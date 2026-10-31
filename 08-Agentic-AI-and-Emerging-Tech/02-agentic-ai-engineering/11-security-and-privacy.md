# Security and Privacy for Agentic Applications

LLM systems add new trust boundaries, but established application security still applies: identity, authorization, input validation, secrets management, encryption, dependency hygiene, and incident response remain essential.

## Threat Model the Full Data Flow

Identify assets, principals, trust boundaries, data flows, tools, providers, retrieval stores, logs, checkpoints, and operators. Include direct user input, retrieved documents, model output, tool responses, background workers, and remote protocol servers.

## Core Threats and Controls

| Threat | Example | Primary controls |
|---|---|---|
| Prompt injection | A document tells the model to reveal another record | Treat content as untrusted; enforce ACL in tools/retrieval; never put policy only in prompts. |
| Excessive agency | Model invokes a write action outside task scope | Narrow tool allowlists, policy checks, step budgets, approvals, kill switch. |
| Broken object-level authorization | Tool accepts a model-supplied foreign object ID | Derive principal from verified identity; authorize every object access in domain service. |
| Sensitive data disclosure | PII appears in provider request, trace, or cache | Minimize and classify data; redact logs; restrict egress; define retention. |
| Insecure output handling | Generated string becomes HTML, SQL, shell, or an API command | Treat output as untrusted; use typed APIs, escaping, parameterization, validation. |
| Retrieval poisoning | Malicious or stale content enters the index | Source governance, provenance, review, versioning, quarantine, deletion/rebuild. |
| Denial of wallet | Huge context or repeated tool/model loop drives cost | Request and per-tenant quotas, token limits, max steps, deadlines, alerts. |
| Supply-chain compromise | Malicious model, package, tool server, or prompt update | Pin/review dependencies, verify artifacts, approve tools, version and sign releases. |

## Identity and Authorization Rules

- The model is not a principal. It cannot grant itself access or consent.
- Pass verified identity through a trusted application context, not as a prompt instruction.
- Authorize every read and write at the service boundary, including background jobs and checkpoint resumes.
- Use separate workload identities and least-privilege credentials for model, database, storage, and tools.
- Bind human approval to a specific action and payload; revalidate authorization when the action executes.

## Privacy Lifecycle

Classify input before provider routing. Minimize, redact, or tokenize sensitive fields when feasible. Document provider retention and training settings. Define storage and retention separately for source documents, extracted fields, prompts, traces, conversation history, caches, and graph checkpoints. Ensure deletion propagates to derived indexes and backups according to policy.

## Security Testing

Test indirect prompt injection in retrieved documents, cross-tenant access, tool argument tampering, malformed model output, oversized inputs, provider timeouts, sensitive-data leakage in logs, and replayed side effects. Include adversarial cases in the release gate, not only manual red-team exercises.

Related references: [agentic AI threats](../01-agentic-ai/25-agentic-ai-threats.md), [agent identity](../01-agentic-ai/26-agent-identity-and-secure-access.md), [data governance](../01-agentic-ai/27-ai-data-governance.md), and the handbook's [security section](../../03-Security/README.md).