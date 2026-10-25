# Event-Driven Agent Workflows

## Scope

Queues, events, sagas, idempotency, deduplication, and backpressure.

## Topics

- Event and command boundaries for agent work.
- Queue-based asynchronous execution and status tracking.
- Sagas and compensation for multi-system side effects.
- Duplicate delivery, ordering, replay, dead letters, and poison messages.
- Backpressure, rate limits, fairness, and workload isolation.

## Architect questions

- What is the event contract and versioning policy?
- Is processing at-least-once, at-most-once, or effectively-once?
- How does the system behave during dependency overload?
