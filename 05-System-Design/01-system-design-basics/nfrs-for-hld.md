# Non-functional Requirements for High-Level Design

Non-functional requirements (NFRs) describe the qualities, constraints, and operating conditions a system must satisfy. They shape architecture only when they are specific enough to guide a decision and a verification plan.

## Common quality attributes

| Attribute | Make the requirement measurable with | Focused chapter |
| --- | --- | --- |
| Performance | Latency percentiles, throughput, and workload | [API performance](api-performance.md) |
| Scalability | Expected growth, peak load, and capacity limits | [Scalability](scalability.md) |
| Availability and reliability | Availability target, error budget, and recovery expectations | [Resilience and fault tolerance](../02-distributed-systems/resiliency-vs-fault-tolerance.md) |
| Security and privacy | Data classification, access boundaries, and applicable controls | [Security](../../03-Security/README.md) |
| Observability | Required signals, alert conditions, and diagnostic coverage | [Observability](observability.md) |
| Consistency and durability | Read/write guarantees and acceptable data-loss window | [Consistency approaches](../02-distributed-systems/different-ways-to-achieve-consistency.md) |
| Maintainability and operability | Ownership, deployment, support, and change expectations | [Operational excellence](../../04-Cloud-and-DevOps/01-devops/operational-excellence.md) |
| Cost efficiency | Budget, unit cost, and cost-growth limits | [System-design trade-offs](system-design-trade-offs.md) |

The table is a checklist, not a requirement to optimize every attribute equally. Choose the attributes that matter for the product and make conflicts explicit.

## Turn qualities into requirements

For each selected attribute:

1. State the user or business outcome it protects.
2. Define the workload, environment, and measurement window.
3. Set a target and a failure threshold, including what happens when the target is missed.
4. Identify the design decision affected by the target.
5. Name how the team will verify it, such as a load test, recovery exercise, security review, or production SLI.

Avoid unbounded statements such as "the system must be fast" or "highly available." For example, a requirement can specify p95 latency for a named endpoint at a stated request rate, or a monthly availability objective with a defined measurement scope.

## Use during design

Capture the chosen targets with functional requirements and workload estimates before drawing the architecture. Review trade-offs explicitly: stronger consistency may add latency, redundancy raises cost and operational complexity, and aggressive retries can worsen overload. See [system-design trade-offs](system-design-trade-offs.md) and the [HLD process](hld-process.md).

## Further reading

- [Google SRE: Service Level Objectives](https://sre.google/sre-book/service-level-objectives/)
- [AWS Well-Architected Framework](https://docs.aws.amazon.com/wellarchitected/latest/framework/welcome.html)
