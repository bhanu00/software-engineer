# State Machines and Workflow Recovery

## Scope

State machines, graphs, planning, routing, retries, checkpoints, timeouts, and compensation.

## Topics

- Explicit state, transitions, guards, and terminal states.
- Planning and routing with bounded steps and budgets.
- Retryable versus non-retryable failures.
- Durable checkpoints, resume, timeout, cancellation, and compensation.
- Idempotency and recovery after partial completion.

## Architect questions

- Can an interrupted workflow resume safely?
- What side effects require compensation?
- How are stuck, looping, or abandoned runs detected?
