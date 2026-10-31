# Context and Memory

An LLM has no automatic, reliable memory of your application. It processes the context included in a particular request. A production system decides what to retrieve, what to retain, how long to retain it, and who may access it.

## Five Different Things Often Called Memory

| Type | Meaning | Enterprise example |
|---|---|---|
| **Prompt context** | Information assembled for one model call | Current question, authorized document excerpts, and evidence references. |
| **Conversation history** | Recent turns or a summary for continuity | Recent assistant interactions and a short rolling summary. |
| **Workflow state** | Data needed to continue this job or graph execution | A document review run waiting for an approver. |
| **Durable user data** | User-approved facts that belong to the application domain | Saved preferences, selected workflow outcome, and task progress. |
| **Shared knowledge** | Organization content available to eligible users | Versioned policy manuals and technical standards in a retrieval system. |

Conversation history, durable profile data, graph checkpoints, and RAG knowledge are different stores with different owners and lifetimes. Avoid one vague `memory` table for all of them.

## Context Assembly

For each model call, construct a small, purpose-specific context:

```text
system policy and task instructions
+ current user request
+ authorized profile facts relevant to this task
+ recent turns or a summary when continuity matters
+ retrieved, permission-checked resources with source identifiers
+ tool results needed for the next decision
```

Use relevance, permissions, freshness, and token budget to select context. Summaries are lossy: preserve decisions, unresolved questions, and source references; do not treat a summary as the authoritative profile.

## Example Memory Lifecycle

```text
User says: "Use the latest approved policy, and only include documents from my team."
  -> use the statement for the current response
  -> resolve "latest approved policy" through authorized metadata filters
  -> return evidence references and record the selected policy version
  -> load only the authorized preference in future relevant workflows
```

Do not infer durable personal traits from a single message. Let users or administrators inspect, correct, and delete retained facts according to policy. Apply purpose limitation and stricter controls to sensitive information.

## Possible Storage Choices

- **Redis/cache:** Recent context and summaries with a deliberate TTL. It is useful for speed, but should not be the sole store if a conversation or workflow must survive beyond that TTL.
- **DynamoDB or another durable database:** User-owned profile facts, plans, conversation records, and audit events, each with explicit access and retention rules.
- **LangGraph checkpointer:** Per-run or per-thread graph state needed for resumption. Choose a backend whose durability matches the workflow; a checkpoint is not automatically semantic memory.
- **Vector store / knowledge base:** Shared, versioned resources or approved user documents when semantic retrieval is justified. Enforce document-level access controls and deletion propagation.

See [RAG and knowledge engineering](08-rag-and-knowledge-engineering.md) for shared knowledge retrieval and [enterprise AI architecture](09-enterprise-ai-architecture.md) for tenant isolation and system boundaries.

## Design Checklist

- What user outcome needs this information later?
- Is this ordinary product data, temporary workflow state, or actual personalization memory?
- What is the source, timestamp, confidence, and expiry of the fact?
- Can the user inspect, correct, withdraw consent, and delete it?
- Does every retrieval enforce the authenticated user's ownership and tenant boundary?
- Could the same result be achieved with less data or a shorter retention period?

See the companion [agent memory reference](../01-agentic-ai/9-agent-memory.md) for architect-level questions.