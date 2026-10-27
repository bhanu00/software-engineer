# AI in DevOps

AI can assist delivery and operations by summarizing signals, retrieving runbooks, and proposing bounded actions. It should improve an engineer's decision loop, not silently take ownership of production changes.

## Useful applications

- **Change risk:** combine code, deployment, and service context to highlight risky changes for human review.
- **Incident triage:** summarize alerts, recent deployments, traces, and relevant runbooks with links to the source evidence.
- **Log and trace exploration:** translate a question into read-only queries, explain results, and identify missing telemetry.
- **Runbook assistance:** retrieve operational procedures and guide an operator through verified steps.
- **Pipeline feedback:** explain build and test failures and suggest small, reviewable fixes.
- **Capacity and cost analysis:** identify unusual trends and generate hypotheses for an engineer to validate.

## A safe operating model

1. Start with read-only access to a narrow set of approved telemetry and documentation.
2. Require citations or direct links to evidence for diagnoses and recommendations.
3. Keep secrets, customer data, and unrelated tenant data out of model context.
4. Put deterministic policy checks around proposed commands, deployments, and access changes.
5. Require explicit human approval for production mutations, destructive operations, and access-control changes.
6. Log prompts, tool calls, approvals, results, and model versions with appropriate data minimization.
7. Provide a conventional manual workflow when the model or its dependencies are unavailable.

## Evaluation and reliability

Evaluate retrieval quality, factual accuracy, unsafe recommendation rate, time to useful diagnosis, and operator acceptance. Test against historical incidents and adversarial or ambiguous requests. Measure false confidence as well as answer quality.

Treat the assistant as a production dependency: define latency and availability targets, rate limits, timeouts, cost controls, privacy boundaries, and an incident response owner. Do not let a model be the sole authority for health checks, deployment gates, or emergency actions.

## Further study

- [Agentic AI learning roadmap](01-agentic-ai/agentic-ai-learning-roadmap.md)
- [Agentic AI threats](01-agentic-ai/25-agentic-ai-threats.md)
- [Human oversight and incident response](01-agentic-ai/29-human-oversight-and-incident-response.md)
- [Operational excellence](../04-Cloud-and-DevOps/01-devops/operational-excellence.md)
- [Observability](../05-System-Design/01-system-design-basics/observability.md)
