# Enterprise AI Architecture

Enterprise AI architecture extends the application architecture with model access, data boundaries, policy enforcement, and operational control. A model provider is a dependency; it should not become the owner of identity, authorization, or business truth.

## Reference Architecture

```text
Clients
  -> API gateway: authentication, request limits, routing
  -> application/API: authorization, domain contracts, tenancy
  -> AI orchestration: workflow, context assembly, policy and approvals
      -> model gateway: provider routing, quotas, budgets, timeouts
      -> tool gateway: tool catalog, scoped identity, validation, audit
      -> retrieval service: ACL-filtered search, citations, freshness
  -> domain services and data stores: source of truth
  -> async workers/workflow engine: long-running work and recovery

Cross-cutting: evaluation, tracing, governance, security, cost, incident response
```

## Application-Owned Provider Boundary

Define an application interface that captures the capabilities you need rather than leaking one vendor's request format everywhere. Include model identifier, structured-output capability, streaming support, context/output limits, timeout behavior, data handling configuration, and usage metadata. Keep provider-specific adapters behind it. Model fallback is not always transparent: compare quality, policy, privacy, and schema behavior before routing to another provider.

## Model Gateway Responsibilities

- Authenticate workloads to approved model providers using managed credentials.
- Route by task policy, region, data classification, capability, availability, and budget.
- Enforce tenant and workload quotas, max input/output tokens, and deadlines.
- Apply provider-specific safety settings and data-handling constraints.
- Record model and prompt versions, usage, latency, retries, and outcome metadata.
- Support allowlists, canary rollout, rollback, and emergency disablement.

The gateway should not make domain authorization decisions or silently change the meaning of a task when a fallback model is selected.

## Multi-Tenancy

Propagate a trusted tenant and principal identity from the API boundary through workflow state, tools, retrieval, caches, checkpoints, and audit records. Never trust model-generated tenant identifiers. Include tenant identity in storage partitioning or enforce equivalent access controls; prevent cache-key collisions across tenants. Test direct object access, search filters, workflow resume, background jobs, support tooling, and deletion across tenants.

## Control Plane and Data Plane

- **Control plane:** Model and prompt registry, workflow/tool catalog, policy, quotas, tenant configuration, release controls, and evaluation gates.
- **Data plane:** Request execution, context, model calls, retrieval, tool results, workflow state, and output.

Changes in the control plane should be versioned, reviewed, auditable, and gradually rolled out. The execution plane should identify exactly which configuration version handled each run.

## Placement and Service Boundaries

Start as a modular application when ownership and scale permit. Separate model gateway, retrieval, or workflow services only when security, scaling, latency, deployment ownership, or vendor governance requires it. Avoid a central platform that becomes a bottleneck for small teams, and avoid every team independently implementing identity, budgets, and audit.

**Exercise:** draw a trust-boundary diagram for a multi-tenant application. Mark identity propagation, sensitive data, model-provider egress, tool side effects, and operator access. Add a negative test for each boundary.