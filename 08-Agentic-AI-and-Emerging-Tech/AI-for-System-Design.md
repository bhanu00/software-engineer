# AI for System Design

AI tools can accelerate system-design exploration by organizing requirements, comparing alternatives, and identifying questions a team has not answered. They do not replace domain discovery or engineering judgment.

## Where AI can help

- Turn an initial problem statement into candidate functional requirements and quality attributes.
- Generate clarifying questions about scale, latency, consistency, privacy, and cost.
- Draft component and data-flow options for a human to critique.
- Compare storage, messaging, caching, and deployment choices against stated constraints.
- Produce failure-mode checklists and review prompts.
- Summarize design documents, ADRs, and operational feedback for a focused review.

## A disciplined workflow

1. Provide the problem context and explicitly state assumptions; ask the tool to separate facts from guesses.
2. Validate requirements and constraints with stakeholders before discussing technology.
3. Generate multiple candidate designs, then compare them against the same workload and quality attributes.
4. Ask for bottlenecks, failure modes, security boundaries, and operational costs for each candidate.
5. Verify protocol details, limits, and product capabilities against authoritative documentation.
6. Record the final decision, alternatives, evidence, risks, and follow-up measurements in an ADR.

## Questions every design still needs

- What is the workload: read/write ratio, data size, growth, peak patterns, and geographic distribution?
- Which operations require strong consistency, and where is bounded staleness acceptable?
- What happens when a dependency is slow, unavailable, or returns an ambiguous result?
- How are identity, authorization, sensitive data, and trust boundaries handled?
- What are the SLOs, recovery objectives, cost constraints, and operational ownership?
- How will the design be measured and changed as assumptions prove wrong?

## Limits and safeguards

Generated diagrams or recommendations can omit constraints, invent product behavior, or make incompatible components appear coherent. Treat output as a draft. Do not provide confidential designs or credentials to unapproved services, and do not accept a generated design without checking its failure semantics, security model, cost, and operational burden.

## Further study

- [System-design basics](../05-System-Design/01-system-design-basics/README.md)
- [Non-functional requirements for HLD](../05-System-Design/01-system-design-basics/nfrs-for-hld.md)
- [Agentic AI quality dimensions](01-agentic-ai/18-agent-quality-dimensions.md)
- [Agentic AI tracing and observability](01-agentic-ai/19-agent-tracing-and-observability.md)
