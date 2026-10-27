# System-Design Foundations

This chapter is a map into the handbook's system-design material, not a duplicate collection of every reference. Follow the linked chapters in order and use their focused further-reading sections for external sources.

## Learning sequence

1. [System-design basics](README.md): requirements, HLD approach, and trade-offs.
2. [Scalability](scalability.md): capacity, scaling approaches, and bottlenecks.
3. [Quality attributes and focused topics](README.md): non-functional requirements, performance, caching, rate limiting, and observability.
4. [Distributed systems](../02-distributed-systems/README.md): consistency, messaging, coordination, and failure handling.
5. [Architecture](../03-architectures/README.md) and [microservices](../04-microservices/README.md): structural choices and trade-offs.
6. [Case studies](../../07-Case-Studies-and-Use-Cases/README.md): apply the concepts to concrete systems.

## Core concepts

- [Reliability and resilience](../02-distributed-systems/resiliency-vs-fault-tolerance.md)
- [Consistency and CAP-related approaches](../02-distributed-systems/different-ways-to-achieve-consistency.md)
- [Service communication, polling, and messaging](../02-distributed-systems/different-ways-service-to-service-communication.md)
- [Load balancing and network protocols](../02-distributed-systems/network-protocols-and-load-balancer.md)
- [Database selection and scaling](../../02-Databases-and-Data/README.md)
- [Security fundamentals](../../03-Security/README.md)
- [Disaster recovery](../../04-Cloud-and-DevOps/01-devops/disaster-recovery.md)

## Study practice

For each design, write down the requirements, assumptions, workload, non-functional targets, candidate designs, trade-offs, failure modes, and operational plan. Practice explaining one design at multiple levels of detail. The [learning path](../../LEARNING_PATH.md#path-b-system-design-and-distributed-systems) provides a staged schedule; use the [case studies](../../07-Case-Studies-and-Use-Cases/README.md) for practice prompts.
