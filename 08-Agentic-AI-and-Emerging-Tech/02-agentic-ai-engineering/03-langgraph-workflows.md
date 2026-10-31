# LangGraph Workflows

LangGraph represents a workflow as state plus nodes and transitions. It is useful when a request spans steps, branches based on evidence, pauses for a person, or must resume after an interruption. A graph is not automatically an agent: nodes can be deterministic functions, model calls, or bounded tool-selection steps.

## Graph Vocabulary

- **State:** Typed data passed through a workflow. Store only what later nodes need.
- **Node:** A function that reads current state and returns a state update.
- **Edge:** A transition to the next node.
- **Conditional edge:** A transition selected from a validated state value.
- **Checkpointer:** Persists workflow state so execution can resume. It is not the same thing as long-term user memory.
- **Interrupt:** A pause for clarification, approval, or human review.

## Example: Document Analysis Graph Shape

This simplified graph uses known steps and a deterministic confidence policy. The services and model are dependencies injected by the application, not hidden globals.

```python
from typing import TypedDict

from langgraph.graph import END, START, StateGraph


class AnalysisState(TypedDict, total=False):
    principal_id: str
    query: str
    evidence: dict[str, object]
    answer: dict[str, object]
    review_required: bool
    errors: list[str]


def load_evidence(state: AnalysisState) -> dict[str, object]:
    evidence = document_service.search_authorized(
        state["principal_id"], state["query"]
    )
    return {"evidence": evidence}


def draft_answer(state: AnalysisState) -> dict[str, object]:
    answer = answer_model.create_grounded_summary(state["query"], state["evidence"])
    return {"answer": answer}


def validate_answer(state: AnalysisState) -> dict[str, object]:
    validated = answer_schema.validate_citations(state["answer"], state["evidence"])
    needs_review = confidence_policy.requires_human_review(validated)
    return {"answer": validated, "review_required": needs_review}


def next_step(state: AnalysisState) -> str:
    return "human_review" if state["review_required"] else "complete"


builder = StateGraph(AnalysisState)
builder.add_node("load_evidence", load_evidence)
builder.add_node("draft_answer", draft_answer)
builder.add_node("validate_answer", validate_answer)
builder.add_node("human_review", human_review_service.create_case)
builder.add_edge(START, "load_evidence")
builder.add_edge("load_evidence", "draft_answer")
builder.add_edge("draft_answer", "validate_answer")
builder.add_conditional_edges(
    "validate_answer",
    next_step,
    {"human_review": "human_review", "complete": END},
)
builder.add_edge("human_review", END)

# Inject a persistent checkpointer in production; use an in-memory saver in tests.
graph = builder.compile(checkpointer=checkpointer)
```

This is a teaching outline, not copy-paste application code: define and inject the service contracts, graph configuration, checkpointer, identity handling, and error policy in your application. For an interactive approval, use a supported interrupt/resume pattern rather than treating a normal function call as a human pause.

## Graph Design Rules

- Put authorization and domain rules in services that can be tested without LangGraph.
- Make nodes idempotent when retries can repeat them, especially around writes.
- Keep graph state bounded; store references to large documents rather than their full contents.
- Classify failures: retry transient provider/network failures, but do not retry invalid policy decisions forever.
- Persist checkpoints according to the maximum expected pause and recovery window.
- Do not checkpoint secrets or unredacted sensitive text without a deliberate retention and access policy.
- Add explicit maximum steps, model-call budgets, and terminal outcomes.

## Choosing LangGraph Versus a Queue or Workflow Service

Use LangGraph for stateful model-oriented control flow. Keep a queue for asynchronous job delivery and backpressure. For durable processes with long waits, strict timers, compensation, and cross-service transactions, compare a workflow engine such as Step Functions or Temporal rather than assuming an in-process graph alone supplies every operational guarantee.

**Learning exercise:** test each node as a plain Python function first. Then test the compiled graph's routing, failure, checkpoint, and resume behavior using mocked services and model responses.