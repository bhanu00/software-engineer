# Agentic AI Engineering: From Concepts to Production

This track turns the concepts in [01-agentic-ai](../01-agentic-ai/README.md) into a practical engineering sequence. Examples use a generic, multi-tenant document-analysis service and focus on implementation rather than any product's business or market details.

The goal is not to put an agent in every feature. The goal is to learn when a model call, deterministic service, workflow, or bounded agent is appropriate, then build and operate that choice responsibly.

## Before You Start

You should be comfortable with Python, HTTP APIs, Pydantic-style validation, tests, and basic distributed-system ideas such as queues, retries, and idempotency. Review the [Agentic AI learning roadmap](../01-agentic-ai/agentic-ai-learning-roadmap.md) for the broader capability map.

## Learning Sequence

| Step | Guide | Outcome |
|---|---|---|
| 1 | [LLM foundations](../01-agentic-ai/1-llm-concepts.md), [retrieval](../01-agentic-ai/3-retrival-concepts.md), [trade-offs](../01-agentic-ai/5-prompting-rag-finetuning-tradeoffs.md), [deterministic boundaries](../01-agentic-ai/6-deterministic-boundaries.md) | Understand model capabilities, tokens, context limits, embeddings, prompting, model adaptation, and when to use deterministic software. |
| 2 | [Agentic patterns and terminology](01-agentic-patterns.md) | Distinguish an LLM feature, tool call, ReAct loop, agent, and workflow. |
| 3 | [LangChain building blocks](02-langchain-building-blocks.md) | Compose model calls, prompts, tools, structured outputs, and retrieval without hiding the underlying design. |
| 4 | [RAG and knowledge engineering](08-rag-and-knowledge-engineering.md) | Build permission-aware ingestion, retrieval, citations, freshness, and deletion. |
| 5 | [LangGraph workflows](03-langgraph-workflows.md) | Model state, nodes, routing, retries, checkpointing, and human pauses. |
| 6 | [Context and memory](04-context-and-memory.md) | Separate request context, conversation history, workflow checkpoints, durable user data, and shared knowledge. |
| 7 | [Enterprise AI architecture](09-enterprise-ai-architecture.md) | Design model gateways, tenancy boundaries, provider adapters, control planes, and data planes. |
| 8 | [Agent harness and orchestration](05-agent-harness-and-orchestration.md) | Design the policy, tool, model, identity, budget, and audit boundaries around workflows. |
| 9 | [Protocols and interoperability](10-protocols-and-interoperability.md) | Use MCP and agent-to-agent handoffs without confusing protocol with trust. |
| 10 | [Security and privacy](11-security-and-privacy.md) | Threat-model prompts, retrieval, tools, identity, data, and side effects. |
| 11 | [Evaluation and testing](12-evaluation-and-testing.md) | Test deterministic contracts and measure stochastic quality with reviewed datasets. |
| 12 | [Production operations and governance](13-production-operations-and-governance.md) | Deploy, observe, scale, govern, and recover enterprise AI workflows. |
| 13 | [Enterprise workflow capstone](14-enterprise-workflow-capstone.md) | Apply the concepts to a generic, bounded document-analysis workflow. |

## How This Relates to the Existing Notes

This implementation track complements, rather than replaces, the reference material in `01-agentic-ai`:

- [Agent tools and workflows](../01-agentic-ai/7-agents-tools-workflows.md)
- [State machines and recovery](../01-agentic-ai/8-state-machines-and-recovery.md)
- [Agent memory](../01-agentic-ai/9-agent-memory.md)
- [Human in the loop](../01-agentic-ai/11-human-in-the-loop.md)
- [Agent contracts and tool catalogs](../01-agentic-ai/16-agent-contracts-and-tool-catalogs.md)
- [Evaluation-driven development](../01-agentic-ai/17-evaluation-driven-development.md)
- [Tracing and observability](../01-agentic-ai/19-agent-tracing-and-observability.md)
- [Agent SLOs and reliability](../01-agentic-ai/20-agent-slos-and-reliability.md)
- [Prompt/model versioning and releases](../01-agentic-ai/21-prompt-model-versioning-and-releases.md)
- [Unit economics](../01-agentic-ai/22-agentic-ai-unit-economics.md)
- [AI governance operating model](../01-agentic-ai/23-ai-governance-operating-model.md)
- [AI risk frameworks](../01-agentic-ai/24-ai-risk-frameworks-and-regulation.md)
- [Agent threats](../01-agentic-ai/25-agentic-ai-threats.md)
- [Agent identity and secure access](../01-agentic-ai/26-agent-identity-and-secure-access.md)
- [AI data governance](../01-agentic-ai/27-ai-data-governance.md)
- [Quality drift and hallucination](../01-agentic-ai/28-agent-quality-drift-and-hallucination.md)
- [Human oversight and incident response](../01-agentic-ai/29-human-oversight-and-incident-response.md)

## Enterprise Coverage Map

| Enterprise concern | Covered in |
|---|---|
| Model capabilities, prompts, tokens, structured outputs, embeddings | [LLM foundations](../01-agentic-ai/1-llm-concepts.md), [LangChain](02-langchain-building-blocks.md) |
| Deterministic software versus LLMs, agents, and workflows | [Deterministic boundaries](../01-agentic-ai/6-deterministic-boundaries.md), [agentic patterns](01-agentic-patterns.md) |
| RAG ingestion, ACL filtering, freshness, citations, deletion | [RAG engineering](08-rag-and-knowledge-engineering.md) |
| Frameworks, state, retries, checkpoints, human approval | [LangGraph](03-langgraph-workflows.md), [human oversight](../01-agentic-ai/11-human-in-the-loop.md) |
| Context assembly, conversation state, durable memory | [Memory](04-context-and-memory.md), [memory reference](../01-agentic-ai/9-agent-memory.md) |
| Model gateways, provider abstraction, control/data planes, tenancy | [Enterprise architecture](09-enterprise-ai-architecture.md), [orchestration planes](../01-agentic-ai/15-orchestrator-control-and-data-plane.md) |
| Tools, identity, MCP, agent handoffs, least privilege | [Harness](05-agent-harness-and-orchestration.md), [protocols](10-protocols-and-interoperability.md), [agent identity](../01-agentic-ai/26-agent-identity-and-secure-access.md) |
| Threat modeling, privacy, data governance, risk | [Security](11-security-and-privacy.md), [data governance](../01-agentic-ai/27-ai-data-governance.md), [risk frameworks](../01-agentic-ai/24-ai-risk-frameworks-and-regulation.md) |
| Evaluation, testing, quality drift, versioning | [Evaluation](12-evaluation-and-testing.md), [release versioning](../01-agentic-ai/21-prompt-model-versioning-and-releases.md), [quality drift](../01-agentic-ai/28-agent-quality-drift-and-hallucination.md) |
| SLOs, resilience, incident response, cost, governance | [Operations](13-production-operations-and-governance.md), [SLOs](../01-agentic-ai/20-agent-slos-and-reliability.md), [unit economics](../01-agentic-ai/22-agentic-ai-unit-economics.md), [incident response](../01-agentic-ai/29-human-oversight-and-incident-response.md) |

The companion notes in `01-agentic-ai` provide deeper references for event-driven processing, multi-agent collaboration, quality dimensions, tracing, governance, and risk frameworks.

## Working Rules

- Keep authorization, calculations, source-of-truth data, and consequential writes in application code.
- Give models narrow, typed tools; do not expose unrestricted database or shell access.
- Treat generated output as untrusted until validated and checked against evidence.
- Make memory user-scoped, purpose-limited, correctable, and deletable.
- Start with one bounded workflow. Add autonomy only when evaluations and product outcomes justify it.

Return to the [Agentic AI and Emerging Tech stage](../README.md) or the [handbook index](../../INDEX.md).