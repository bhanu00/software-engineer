# System Design Overview

System design turns product requirements and workload constraints into a set of components, data flows, and operational choices. A good design is not the most complex architecture; it is the simplest one that meets the required behavior and quality targets.

## A practical design sequence

1. **Clarify the problem:** identify users, core use cases, scope, assumptions, and constraints.
2. **Define quality attributes:** quantify availability, latency, consistency, durability, security, recovery, and cost goals.
3. **Estimate the workload:** understand request volume, read/write mix, data growth, burstiness, and geographic distribution.
4. **Sketch the interfaces and data:** define APIs, core entities, ownership, and the source of truth.
5. **Draw the high-level components:** show clients, services, storage, caches, queues, and trust boundaries.
6. **Walk through critical flows:** trace normal requests and important asynchronous workflows end to end.
7. **Analyze trade-offs and failures:** identify bottlenecks, dependency failures, consistency choices, and degraded modes.
8. **Cover operations:** explain deployment, observability, security controls, recovery, and how the design will evolve.

## Continue by topic

- [How to approach an HLD](how-to-approach-hld.md)
- [System-design trade-offs](system-design-trade-offs.md)
- [Scalability](scalability.md)
- [Non-functional requirements](../../06-Advanced-Topics/nfrs-for-hld.md)
- [Distributed systems](../02-distributed-systems/README.md)
- [Architecture](../03-architectures/README.md)
- [Case studies](../../07-Case-Studies-and-Use-Cases/README.md)