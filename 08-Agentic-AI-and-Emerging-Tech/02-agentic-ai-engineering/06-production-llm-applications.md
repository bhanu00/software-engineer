# Production LLM Applications

A working demo proves that a model can produce an output. A production feature must also behave acceptably when inputs are adversarial, providers are unavailable, results are wrong, costs rise, and users need to understand or correct the outcome.

## Production Readiness Areas

### Quality and Evaluation

- Create versioned representative cases before prompt tuning.
- Test schema validity, evidence grounding, task success, safe abstention, and correct routing.
- Separate deterministic assertions from human-reviewed quality rubrics.
- Evaluate retrieval independently from generation.
- Track regression by prompt, model, and workflow version; do not rely on exact string snapshots for open-ended answers.

### Security and Privacy

- Enforce authentication and resource ownership before constructing model context.
- Treat user text and retrieved documents as untrusted; defend tools against prompt injection.
- Give each tool least privilege, narrow schemas, result limits, timeouts, and side-effect protections.
- Minimize PII sent to external providers and never log secrets or raw resumes unnecessarily.
- Define retention, deletion, consent, encryption, and provider data-handling expectations.
- Keep policy decisions and high-impact actions outside the model's authority.

### Reliability and Recovery

- Set explicit deadlines, retries with backoff, circuit breakers, and provider fallback policy.
- Use queues for long-running work and idempotency for retried writes.
- Distinguish transient failures from invalid model output and policy rejection.
- Define how a paused workflow resumes and how expired or corrupt state is handled.
- Degrade to deterministic guidance or a clear retry response rather than pretending an LLM succeeded.

### Observability and Cost

Record workflow/version, provider/model, prompt version, token usage, tool names, latency, outcome, retries, and cost where available. Redact content by default. Track quality and human-review rate alongside latency and cost; cheaper or faster is not better if task quality drops.

Set per-request and per-user limits, maximum tool/model steps, output-token bounds, and a global kill switch. Alert on error rates, spend anomalies, quality regressions, and unusual tool use.

## Example Request Path

```text
FastAPI request
  -> authenticate and authorize
  -> create workflow/run ID and enforce quota
  -> execute a short graph or enqueue a long-running job
  -> call model through a provider boundary with timeout and budget
  -> validate output and policy
  -> persist approved domain result with idempotency
  -> return response or job status
  -> emit redacted trace, metrics, and audit record
```

Keep framework and provider code behind application-owned interfaces where portability and testing matter. Test normal code paths with mock model responses; use opt-in integration tests for real providers. Never make ordinary CI depend on a paid model or a developer's local Ollama process.

## Rollout Strategy

1. Run offline golden evaluations and adversarial tests.
2. Enable the feature for internal/test users behind a feature flag.
3. Compare output quality and operational metrics with the existing deterministic path.
4. Expand gradually with a rollback switch and documented owner.
5. Review incidents, user corrections, and evaluation drift; update prompts and tests together.

The existing [evaluation](../01-agentic-ai/17-evaluation-driven-development.md), [tracing](../01-agentic-ai/19-agent-tracing-and-observability.md), [SLO](../01-agentic-ai/20-agent-slos-and-reliability.md), and [threat](../01-agentic-ai/25-agentic-ai-threats.md) notes expand these topics.