# Agent Harness and Orchestration

An agent harness is the controlled runtime around model behavior. LangChain and LangGraph can implement parts of it, but production responsibilities also include application identity, policy enforcement, data access, budgets, audit, and recovery.

## Responsibility Map

```text
Client
  -> API authentication and request validation
  -> workflow orchestrator (known control flow and bounded model decisions)
      -> context builder (authorized, minimal, current)
      -> model gateway (provider, timeout, token and cost budget)
      -> tool gateway (schemas, identity, permissions, limits)
      -> policy checks (allowed actions, approval, stop conditions)
      -> audit and traces (model, tool, state transition, outcome)
  -> domain services and data stores (source of truth)
```

## Control Plane and Execution Plane

- **Control plane:** Workflow definitions, model/provider policy, prompt versions, tool catalog, budgets, rollout flags, and evaluation thresholds.
- **Execution plane:** A single request or run: authenticated context, graph state, model invocations, tool results, retries, and final outcome.

This separation helps explain how a model version or tool can be changed without granting the model policy authority.

## Tool Contract Example

A good tool has one job, typed inputs and outputs, bounded results, a clear permission check, and predictable side effects.

```text
Tool: compare_profile_to_role
Input: authenticated principal (injected), target_role_id
Output: matched skill IDs, gap skill IDs, requirements version
Permission: caller may read their own profile and this published role catalog
Side effect: none
Limit: one role per call; bounded response size
Audit: principal, role ID, result status, latency
```

For a write tool such as `submit_document_review`, require the configured approval, use an idempotency key, validate ownership, and record the resulting review ID. Never let the model provide its own principal, permission, or approval.

## Orchestrator Responsibilities

- Select a workflow using deterministic routing or a constrained classifier.
- Supply the model only the tools and context needed for that task.
- Enforce maximum turns, wall-clock timeout, token/cost budget, and allowed transitions.
- Retry only transient failures with bounded backoff; avoid retrying side effects without idempotency.
- Pause for a user or operator when policy requires it.
- Return explicit terminal outcomes: completed, needs clarification, under review, rejected, or failed.
- Emit trace and audit metadata without logging secrets or unnecessary raw personal content.

## Avoid Premature Multi-Agent Design

Start with domain services and one workflow. Add a specialized agent only when it has a distinct contract, bounded responsibility, independent evaluation, and measurable benefit. Multiple prompts or graph nodes do not automatically require multiple agents.

For related platform material, see [orchestrator control and data plane](../01-agentic-ai/15-orchestrator-control-and-data-plane.md), [agent contracts](../01-agentic-ai/16-agent-contracts-and-tool-catalogs.md), and [secure agent identity](../01-agentic-ai/26-agent-identity-and-secure-access.md).