# Production Operations and Governance

Production AI requires both software operations and accountable governance. A workflow must have a service owner, a quality owner, an incident path, and a defined authority for every consequential action.

## Runtime and Deployment

- Choose synchronous APIs for short bounded calls; use queues or durable workflow engines for long-running work, retries, and human waits.
- Set end-to-end deadlines and propagate cancellation. A model timeout should not leave a request or job indefinitely active.
- Scale API, workers, retrieval, and model-provider concurrency independently where workloads differ.
- Apply backpressure and per-tenant admission control before queues or providers are overwhelmed.
- Use idempotent handlers, bounded retry with jitter, DLQs, replay tooling, and documented poison-message handling.
- Version prompts, models, schemas, workflows, retrieval pipelines, and evaluation datasets. Roll them out independently where practical.
- Test rollback, provider outage, credential rotation, data deletion, and checkpoint compatibility.

## SLOs and Telemetry

Define service and quality objectives by workflow and risk class. Useful signals include availability, end-to-end latency, time-to-first-token, queue age, provider errors, tool failures, retrieval recall, citation validity, human-review rate, user corrections, and cost per successful task.

Trace with a run ID across API, workflow, provider, retrieval, and tools. Store versions and outcome metadata. Do not retain prompts, completions, or source text by default; when content capture is justified for debugging or evaluation, restrict access and retention and record the policy.

## Cost and Capacity Controls

Budget tokens and tool steps per run; cap input size and retrieval count; cache only when authorization and freshness permit; route tasks by measured capability and data policy. Track cost by tenant, workflow, model, and successful outcome. Set alerts and a kill switch for runaway spend.

## Governance Operating Model

Maintain a use-case and model inventory with owner, purpose, data classes, impact/risk classification, provider, versions, evaluation evidence, retention, and human oversight. Define who approves model/provider changes, tool access, production rollout, and exceptions. Review incidents, user/operator complaints, quality drift, and policy changes on a regular cadence.

Document residual risks and human responsibilities; do not describe an automated confidence score as proof that an outcome is safe. For high-impact or regulated uses, obtain domain, legal, privacy, and security review before deployment.

## Incident Playbooks

Prepare response steps for cross-tenant disclosure, prompt/tool abuse, unsafe output, quality regression, provider outage, cost spike, queue backlog, data deletion failure, and compromised tool credentials. Include containment, kill switch, evidence preservation, notification/escalation, recovery, and post-incident evaluation updates.

Related references: [agent SLOs](../01-agentic-ai/20-agent-slos-and-reliability.md), [unit economics](../01-agentic-ai/22-agentic-ai-unit-economics.md), [governance operating model](../01-agentic-ai/23-ai-governance-operating-model.md), [risk frameworks](../01-agentic-ai/24-ai-risk-frameworks-and-regulation.md), and [human oversight and incident response](../01-agentic-ai/29-human-oversight-and-incident-response.md).