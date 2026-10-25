# System-Design Foundations

This chapter is a map into the handbook's system-design material, not a duplicate collection of every reference. Follow the linked chapters in order and use their focused further-reading sections for external sources.

## Learning sequence

1. [System-design basics](README.md): requirements, HLD approach, and trade-offs.
2. [Scalability](scalability.md): capacity, scaling approaches, and bottlenecks.
3. [Advanced topics](../../6-Advanced-Topics/README.md): API performance, caching, rate limiting, networking, and non-functional requirements.
4. [Distributed systems](../2-distributed-systems/README.md): consistency, messaging, coordination, and failure handling.
5. [Architecture](../3-architectures/README.md) and [microservices](../4-microservices/README.md): structural choices and trade-offs.
6. [Case studies](../../7-Case-Studies-and-Use-Cases/README.md): apply the concepts to concrete systems.

## Core concepts

- [Reliability and resilience](../2-distributed-systems/resiliency-vs-fault-tolerance.md)
- [Consistency and CAP-related approaches](../2-distributed-systems/different-ways-to-achieve-consistency.md)
- [Service communication, polling, and messaging](../2-distributed-systems/different-ways-service-to-service-communication.md)
- [Load balancing and network protocols](../../6-Advanced-Topics/network-protocols-and-load-balancer.md)
- [Database selection and scaling](../../2-Databases-and-Data/README.md)
- [Security fundamentals](../../3-Security/README.md)
- [Disaster recovery](../../4-Cloud-and-DevOps/1-devops/disaster-recovery.md)

## Study practice

For each design, write down the requirements, assumptions, workload, non-functional targets, candidate designs, trade-offs, failure modes, and operational plan. Practice explaining one design at multiple levels of detail. The [learning path](../../LEARNING_PATH.md#path-b-system-design-and-distributed-systems) provides a staged schedule; use the [case studies](../../7-Case-Studies-and-Use-Cases/README.md) for practice prompts.
