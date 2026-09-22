# Human-in-the-Loop Agent Systems

## Scope

Approval, risk-based routing, escalation, refusal, and safe side effects.

## Topics

- Classifying actions by risk and required approval level.
- Presenting evidence, proposed action, permissions, and expiry to reviewers.
- Approve, reject, revise, cancel, and emergency-stop paths.
- Escalation when confidence is low or policy is ambiguous.
- Auditability, reviewer workload, response time, and override metrics.

## Architect questions

- Which actions require a human and who owns the decision?
- Can approval be bound to the exact proposed side effect?
- What happens when no reviewer is available?
