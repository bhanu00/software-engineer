# Orchestrator Control Plane and Data Plane

## Scope

Separate platform control responsibilities from runtime agent execution.

## Topics

- Control plane: registration, policy, routing, budgets, versions, and tenancy.
- Data plane: workflow execution, model calls, tools, state, and results.
- Agent lifecycle, configuration, deployment, and ownership metadata.
- Isolation, quotas, kill switches, and provider failover.
- Platform APIs and operational interfaces.

## Architect questions

- What must be centralized for safety and consistency?
- What can product teams own independently?
- How does the platform remain available when the control plane is degraded?
