# Capstone: Enterprise Document-Analysis Workflow

This capstone is a generic technical exercise for a multi-tenant service that ingests documents, extracts validated metadata, retrieves authorized evidence, and drafts a cited response for a reviewer. It contains no product-specific examples or private data.

## System Constraints

- Python API with authenticated principals and tenant-scoped data.
- Object storage for source documents and a queue for asynchronous processing.
- A primary database for document metadata, workflow status, and audit records.
- Model-provider calls behind an application-owned interface.
- Deterministic validation and persistence; model output is untrusted input.
- Reviewer approval is required before a designated external side effect.
- Users and operators need status, traceability, retention, and deletion behavior.

## End-to-End Workflow

```text
authenticated upload request
  -> validate tenant, file type, size, and policy
  -> store encrypted source object and enqueue an idempotent job
  -> extract text and scan for unsupported or unsafe content
  -> classify and extract metadata with a bounded model call
  -> validate schema and normalize deterministic fields
  -> chunk, embed, and index with tenant and ACL metadata
  -> answer a query using permission-filtered retrieval and citations
  -> validate citations and policy
  -> pause for reviewer approval when required
  -> perform approved action through a least-privilege tool
  -> persist outcome and emit redacted audit/trace data
```

## Architecture Decisions to Produce

1. **API and async boundary:** Which operations are synchronous, and which belong in the queue worker? Define status resources, idempotency keys, retry policy, and DLQ handling.
2. **Provider boundary:** Define a model interface, capability declaration, timeout, token limits, retry policy, privacy configuration, and fallback behavior. Avoid assuming that model vendors support identical structured output.
3. **RAG design:** Choose chunking and embedding strategy, index metadata, access filters, citations, re-indexing, freshness, and deletion propagation.
4. **Workflow design:** Decide whether a direct function pipeline, LangGraph, or durable workflow service best fits branching, checkpointing, human pauses, and recovery requirements.
5. **Memory design:** Separate conversation history, workflow checkpoints, durable application data, and shared knowledge. Set purpose, owner, TTL, and deletion behavior for each.
6. **Tool and side-effect policy:** Define narrow schemas, authorization, approval, rate limits, idempotency, and audit for every tool.
7. **Operations:** Define SLOs, dashboards, alerts, model and prompt rollout, evaluation gates, budget limits, and kill switches.

## Required Deliverables

- C4 context and container diagrams plus a sequence diagram for normal and failure paths.
- Threat model and data-flow inventory, including tenant isolation and prompt-injection paths.
- ADRs for framework selection, provider interface, retrieval store, checkpoint store, and async execution.
- Typed request, state, tool, and output contracts.
- Unit, integration, contract, adversarial, evaluation, and recovery tests.
- Evaluation dataset with documented provenance, access controls, and a reviewed quality threshold.
- Runbook for provider outage, queue backlog, quality regression, data deletion, and suspected tool misuse.
- Cost model covering model tokens, embeddings, retrieval, storage, compute, observability, and human review.

## Acceptance Tests

- A principal cannot retrieve another tenant's object or index entry, including through model-generated search terms.
- A duplicate queue delivery does not create duplicate completed records or external actions.
- Invalid model output cannot overwrite validated metadata.
- Retrieved content cannot grant itself access or override system policy.
- Every displayed citation refers to a retrieved, authorized source span.
- Reviewer approval is tied to the exact action and payload being approved.
- A retry after a transient model failure is bounded; a permanent validation failure reaches a terminal state.
- Data deletion removes source objects, derived chunks/embeddings, caches, and applicable workflow state according to the retention policy.
- Logs avoid raw document text and secrets while preserving enough information to diagnose outcomes.
- A provider outage follows the documented fallback or graceful-failure path and meets the defined SLO behavior.

## Completion Criteria

The capstone is complete when the architecture, security and data controls, quality evaluation, operational runbooks, and failure recovery are documented and testable. A successful model response alone is not completion.
