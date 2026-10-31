# Agentic Patterns and Terminology

Before choosing LangChain or LangGraph, identify what kind of behavior the system needs. Framework choice follows the workflow; it should not define it.

## The Building Blocks

- **LLM call:** Input instructions and context; receive generated output. No tool use is implied.
- **Structured LLM feature:** An LLM call whose output must satisfy a schema, such as a document classification or extraction result.
- **Tool:** A named, typed application capability, such as `load_role_requirements` or `calculate_skill_gaps`.
- **Workflow:** Application-owned sequence and branching. The steps and transitions are known in advance.
- **Agent:** A model is allowed to select among a bounded set of actions, often repeatedly, based on observations.
- **Orchestration:** Coordination of those model calls, tools, workflow state, retries, approvals, and outcomes.

These are not mutually exclusive. A workflow can contain an agentic step, while the surrounding system remains deterministic.

## ReAct: Reason and Act

ReAct is a tool-use pattern: the model decides what information or action it needs, calls a tool, observes the result, and continues or returns. It is not a framework and does not mean the model should have unlimited autonomy.

```text
Question
  -> select an allowed read-only tool
  -> receive an observation
  -> decide whether more evidence is needed
  -> produce a validated answer
```

For a document question, a bounded loop might call `search_authorized_documents`, then `fetch_document_excerpt`, then summarize with source references. The application still performs access checks and deterministic comparisons. It should not let the model decide which tenant's documents to read.

Production systems should record observable decisions, tool names, inputs/outputs as permitted, and results. Do not expose or depend on hidden chain-of-thought; use concise rationales and evidence references instead.

## Choose the Least Autonomous Pattern That Works

| Pattern | Use when | Enterprise example |
|---|---|---|
| Deterministic service | Rules and calculations are known | Normalize skills and calculate gaps. |
| Single LLM call | One bounded interpretation or generation is needed | Extract fields from a document into a validated schema. |
| Fixed workflow | Steps and branches are known | Ingest, classify, retrieve evidence, draft a summary, validate citations. |
| Bounded agent loop | The model must select among a few safe tools to resolve a request | Assistant chooses between searching an approved index and fetching an authorized excerpt. |
| Multi-agent system | Independent roles have measurable value and explicit coordination | Only when decomposition improves quality or operations enough to justify coordination cost. |

## Framework Roles

- **LangChain** offers reusable model, prompt, output, tool, and retrieval integrations. It is optional; direct provider SDKs can be appropriate behind an application-owned interface.
- **LangGraph** models stateful graphs and control flow: nodes, edges, conditional routing, checkpoints, and pauses.
- **Agentic harness** is the broader runtime around an agent: identity, policy, tool permissions, context, model access, budgets, observability, and recovery. A framework alone is not a production harness.

Use the [agent workflow reference](../01-agentic-ai/7-agents-tools-workflows.md) and [state-machine guide](../01-agentic-ai/8-state-machines-and-recovery.md) for deeper patterns.

## Exercise

For document ingestion, classification, retrieval, summarization, and approval, label each step as deterministic, model-assisted, or agent-selected. For every model-selected action, write down the allowed tool set, authorization source, maximum call count, and stop condition.