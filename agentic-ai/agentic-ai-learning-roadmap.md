# Agentic AI Learning Roadmap

This is a high-level roadmap for an experienced software engineer moving toward
AI Architect, Principal Engineer, or AI Engineering leadership roles. It focuses
on the capabilities required to design, ship, operate, and govern agentic AI in
an enterprise. Use it as a reference map, not as a framework-by-framework course.

## Target capability

By the end, you should be able to:

- Decide when to use a deterministic service, workflow, single agent, or multi-agent system.
- Design production AI systems across model, data, application, cloud, security, and operations layers.
- Establish quality, evaluation, observability, cost, governance, and human-approval controls.
- Lead architecture decisions, product roadmaps, adoption, and value realization.
- Explain technical trade-offs to engineers, security teams, product leaders, and executives.

## Stage 1: Foundations and AI application engineering

**Goal:** Understand the building blocks of LLM applications and retrieval systems.

### Learn

- LLM capabilities and limitations, context windows, tokens, inference, latency, and cost.
- Prompt and context engineering, structured output, model routing, and tool calling.
- Embeddings, vector search, chunking, reranking, metadata filters, and knowledge freshness.
- RAG architecture, citations, abstention, access-aware retrieval, and data ingestion.
- Prompting versus RAG versus fine-tuning versus traditional software or ML.
- Deterministic boundaries: authorization, calculations, business rules, and source-of-truth data.

### Become familiar with

- Hugging Face Transformers, one hosted model API, and one cloud model platform such as AWS Bedrock.
- LangChain or LlamaIndex for RAG abstractions, while understanding the underlying primitives.
- A vector store such as OpenSearch, pgvector, Pinecone, or Weaviate.
- Python or TypeScript, typed schemas, APIs, testing, and CI/CD.

### Outcome

Design a grounded assistant or RAG application with typed outputs, citations,
access control, basic evaluation, cost tracking, and a clear threat model.

## Stage 2: Agentic workflows and protocols

**Goal:** Move from isolated model calls to reliable, multi-step business workflows.

### Learn

- Agents versus tools versus workflows; autonomy as an explicit design choice.
- State machines, graphs, planning, routing, retries, checkpoints, timeouts, and compensation.
- Short-term, task, and long-term memory with appropriate retention and privacy policies.
- Event-driven workflows, queues, sagas, idempotency, deduplication, and backpressure.
- Human-in-the-loop approval, risk-based routing, escalation, refusal, and safe side effects.
- Multi-agent roles, delegation, shared state, arbitration, and when multi-agent designs add complexity.
- MCP host/client/server concepts, tool discovery, authentication, consent, and isolation.
- A2A-style handoffs, capability discovery, identity, trust, and protocol versioning.

### Become familiar with

- LangGraph or an equivalent graph/workflow engine.
- MCP clients and servers, tool gateways, OAuth/OIDC, IAM, and secrets management.
- Temporal, AWS Step Functions, queues, or another durable workflow platform.
- Integrations with source control, issue tracking, calendars, email, SaaS, and enterprise data platforms.

### Outcome

Design a workflow where every side effect has an owner, authorization check,
approval policy, audit trail, timeout, retry strategy, and recovery path.

## Stage 3: Orchestration, platform, and agentic harness

**Goal:** Scale individual agents into a reusable, observable, and reliable platform.

### Learn

- Orchestrator control plane and data plane responsibilities.
- Agent contracts, tool catalogs, routing, tenancy, quotas, budgets, and kill switches.
- Evaluation-driven development: golden datasets, deterministic checks, rubric grading, replay, and red teaming.
- Quality dimensions: task success, groundedness, safety, latency, cost, and human-review rate.
- Tracing model calls, retrieval, tool calls, state transitions, prompts, versions, and outcomes.
- SLOs, graceful degradation, circuit breakers, provider fallback, capacity, and incident response.
- Prompt/model versioning, canary releases, rollback, feature flags, and CI/CD gates.
- Unit economics: model, retrieval, compute, storage, observability, and human-review costs.

### Become familiar with

- LangGraph orchestration, AWS EKS or serverless deployment, and MCP hubs or gateways.
- OpenTelemetry, Grafana, Prometheus, Arize, or Weights & Biases.
- Jenkins or GitHub Actions, Terraform or CloudFormation, and contract/load/security testing.

### Outcome

Design a platform where another team can onboard an agent using documented
contracts, standard evaluations, observability, security controls, and cost limits.

## Stage 4: Governance, security, and responsible AI

**Goal:** Make enterprise AI safe, compliant, explainable, and operationally defensible.

### Learn

- AI governance operating models, ownership, model inventories, risk classification, and audit evidence.
- NIST AI RMF, EU AI Act concepts, privacy, accessibility, records management, and sector controls.
- Threats: direct and indirect prompt injection, data poisoning, model extraction, tool abuse, supply chain, and denial of wallet.
- Identity propagation, least privilege, tenant isolation, scoped credentials, just-in-time access, and secure gateways.
- Data classification, PII/PHI/PCI handling, residency, encryption, retention, deletion, and lineage.
- Hallucination, groundedness, retrieval drift, model behavior changes, and workflow outcome monitoring.
- Human oversight, explanations, appeals, overrides, safe shutdown, and incident response.

### Become familiar with

- IAM, Secrets Manager, KMS, private networking, API gateways, DLP, and policy-as-code.
- Red-team testing, dependency/container scanning, model cards, system cards, and risk registers.
- AI observability and evaluation platforms such as Arize or Weights & Biases.

### Outcome

Produce a threat model, risk register, control map, governance checklist, model
inventory, and incident playbook for a production agent.

## Stage 5: AI architecture and enterprise leadership

**Goal:** Operate at Architect, Principal, or Director scope by connecting strategy,
delivery, technology, people, and measurable business value.

### Product and strategy

- Select use cases by business impact, feasibility, risk, data readiness, and adoption friction.
- Own the roadmap for orchestrators, agent fleets, consoles, dashboards, integrations, and shared services.
- Sequence MVP, pilot, scale, and retirement based on telemetry and user feedback.
- Measure cycle time, throughput, quality, adoption, cost, capacity unlocked, and realized value.
- Make explicit trade-offs across scope, speed, quality, security, maintainability, and cost.

### Enterprise architecture and delivery

- Design multi-tenant, multi-region, hybrid, regulated, and cloud SaaS deployments.
- Integrate AI with enterprise identity, data platforms, developer platforms, and existing systems.
- Evaluate build, buy, partner, and open-source options, including portability and exit strategy.
- Define reference architectures, paved roads, ownership boundaries, and platform APIs.
- Apply Lean/Agile delivery, estimation, work sizing, dependency management, and risk tracking.
- Coordinate product, engineering, data science, security, legal, InfoSec, operations, and partners.

### People and executive leadership

- Hire and grow agent engineers, platform engineers, applied scientists, product managers, SREs, and delivery leaders.
- Build distributed pods with clear accountability and a continuous-learning culture.
- Coach managers and senior engineers; establish expectations, feedback, and career growth.
- Present executive updates that connect delivery, risks, staffing, cost, compliance, and outcomes.
- Communicate architecture at implementation, trade-off, and business levels.

### Outcome

Produce an AI platform strategy, reference architecture, 90-day roadmap, value
scorecard, operating model, hiring plan, and executive decision memo.

## Capstone: Enterprise agent delivery engine

Design a reference platform for an internal productivity or software-delivery workflow:

```text
request -> classify -> retrieve context -> plan -> call approved tools
        -> produce evidence -> human approval -> execute side effect
        -> validate outcome -> report metrics -> audit
```

The capstone should demonstrate:

- An orchestrator and specialized agents with explicit contracts.
- MCP tools for source control, issue tracking, and notification or calendar integration.
- Durable state, retries, idempotency, timeouts, dead-letter handling, and human approval.
- RAG with access control, citations, freshness, and ingestion versioning.
- Evaluation gates, adversarial tests, traces, dashboards, SLOs, and cost budgets.
- IAM, secrets management, PII controls, tenant boundaries, audit events, and kill switches.
- A product roadmap, risk register, value scorecard, and adoption plan.

## Recommended evidence

Maintain a small portfolio of architect-level artifacts:

- A production-style agent system with design document, ADRs, tests, evals, traces, SLOs, and cost analysis.
- An architecture review comparing viable alternatives and recording the decision.
- A governance and threat-model package with controls and residual risks.
- A value-realization narrative showing baseline, adoption, and measured outcomes.
- Leadership stories covering ambiguity, delivery, conflict, incident response, hiring, coaching, and executive influence.

## Companion sections

- [Generative AI overview](gen-ai.md)
- [System design](../system-designs/README.md)
- [Architecture](../architectures/README.md)
- [Distributed systems](../distributed-systems/README.md)
- [Cloud, DevOps, and GitOps](../devops/README.md)
- [Security](../security/README.md)
- [Career preparation](../career/README.md)
- [Solutions and POCs](../solutions/README.md)
