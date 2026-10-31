# Evaluation and Testing

Agent quality is a system property. Evaluate model output, deterministic components, retrieval, tool use, policy decisions, workflow recovery, and user outcomes. Keep routine CI independent from paid or locally hosted model availability.

## Evaluation Layers

1. **Unit tests:** Domain logic, schema validation, normalization, authorization, confidence policy, and node functions.
2. **Contract tests:** Provider adapters, model output schemas, tool input/output contracts, and protocol compatibility.
3. **Integration tests:** Storage, queues, retrieval filters, checkpointers, and workflow transitions using local services or faithful fakes.
4. **Offline evaluations:** Reviewed examples scored for task success, groundedness, citation correctness, safe abstention, and policy behavior.
5. **Adversarial tests:** Prompt injection, data exfiltration attempts, tenant crossover, malformed tool arguments, and cost exhaustion.
6. **Production monitoring:** Drift, correction rates, abandonment, escalation rates, latency, cost, and incidents, with privacy-preserving telemetry.

## Golden Dataset Design

Each case should specify input, permitted context, expected evidence or behavior, forbidden behavior, risk class, and scoring method. Record dataset provenance, consent/licensing as applicable, privacy classification, reviewer, and version. Keep train/tuning examples separate from release evaluation cases to reduce overfitting.

Use deterministic checks for contracts and policy (for example, every cited source ID was retrieved and authorized). Use reviewed rubrics for semantic quality. LLM-as-judge can help triage but is not an authoritative sole gate; calibrate it against human reviewers and measure disagreement.

## Example Test Shape

```python
def test_answer_citations_are_authorized(retrieved_sources, generated_answer):
    validated = answer_schema.model_validate(generated_answer)
    allowed_ids = {source.id for source in retrieved_sources}

    assert validated.citations
    assert all(citation.source_id in allowed_ids for citation in validated.citations)
```

This verifies a deterministic property, not whether the answer is substantively correct. Add separate evaluation criteria for relevance, completeness, and calibrated abstention.

## Release Gates

- No critical authorization, privacy, or tool-safety regression.
- Schema and workflow contract tests pass.
- Quality and groundedness metrics meet reviewed thresholds by risk segment.
- Latency and cost remain within budgets.
- Prompt, model, retrieval, and workflow versions are identified in evaluation results.
- Rollback and kill-switch behavior is tested.

Related references: [evaluation-driven development](../01-agentic-ai/17-evaluation-driven-development.md), [quality dimensions](../01-agentic-ai/18-agent-quality-dimensions.md), and [quality drift](../01-agentic-ai/28-agent-quality-drift-and-hallucination.md).