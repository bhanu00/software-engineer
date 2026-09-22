# Deterministic Boundaries

## Scope

Keep authorization, calculations, business rules, and source-of-truth data outside the model.

## Topics

- Deterministic validation before and after model calls.
- Authorization based on verified identity and policy, never model claims.
- Financial, date, scoring, and eligibility calculations in code.
- Source-of-truth reads and writes through controlled services and tools.
- Typed model outputs, safe defaults, idempotency, and audit events.

## Architect questions

- Which decisions must always be reproducible?
- Which model outputs are suggestions rather than authority?
- Where are policy checks enforced if the model is wrong or compromised?
