# Microservices and Monoliths

Microservices are an architectural choice, not a default upgrade from a monolith. Choose service boundaries and deployment independence only when they solve a concrete organizational or technical problem.

## Monolith

A monolith packages an application as one deployable unit. It is often a strong starting point because it keeps local calls simple, supports straightforward transactions, and has a smaller operational footprint. As the codebase grows, teams need deliberate modular boundaries to prevent unrelated features from becoming tightly coupled.

![Monolithic application diagram](https://github.com/bhanu00/system-design/assets/24689682/61eabde7-1549-4821-9126-8f974ea80e47)

## Microservices

A microservices architecture divides a product into independently deployable services organized around business capabilities. Services communicate through explicit APIs or asynchronous messages and may be scaled or implemented independently.

![Microservices architecture diagram](https://github.com/bhanu00/system-design/assets/24689682/e500f8f4-6213-42f3-86d3-ca2d3ac37ee0)

Potential benefits include independent deployment, targeted scaling, and clearer ownership. These benefits come with distributed-system costs: network failures, data ownership and consistency challenges, observability requirements, service discovery, deployment coordination, and a larger operational surface.

![Microservices scaling diagram](https://github.com/bhanu00/system-design/assets/24689682/90db66ad-94bf-47a4-a452-4eb499d2016a)

An API gateway can front either a monolith or a set of services; using a gateway does not require adopting microservices.

![API gateway diagram](https://github.com/bhanu00/system-design/assets/24689682/278d9f81-f613-4643-9fa0-e7be9f8c08a5)

## Decision checklist

- Do business capabilities have stable boundaries and clear data ownership?
- Do teams need independent delivery or scaling often enough to justify separate deployables?
- Can the organization operate service discovery, observability, incident response, and deployment automation?
- How will cross-service workflows handle retries, duplicate messages, partial failure, and compensation?
- Would a modular monolith solve the current problem with less operational complexity?

Start with a modular monolith when boundaries or requirements are still changing. Extract a service when independent ownership, scaling, deployment, or fault isolation has a measurable benefit.

## Related topics

- [System-design trade-offs](../1-system-design-basics/system-design-trade-offs.md)
- [Service-to-service communication](../2-distributed-systems/different-ways-service-to-service-communication.md)
- [Cascading failures](../2-distributed-systems/cascading-failure.md)
- [CQRS and event sourcing](../3-architectures/cqrs-with-event-sourcing-pattern.md)
- [Outbox pattern](../3-architectures/2pc-vs-outbox-pattern.md)
- [Rate limiting](../../6-Advanced-Topics/rate-limiting.md)

## Further reading

- [Database proxies and why to use them](https://medium.com/@danielaaronw/database-proxies-and-why-you-should-use-them-e44166f3b47b)
- [Amazon RDS Proxy](https://aws.amazon.com/rds/proxy/)
- [Database proxy overview](https://programmingbrain.com/2022/11/what-is-a-database-proxy)
- [Death by a thousand microservices](https://renegadeotter.com/2023/09/10/death-by-a-thousand-microservices.html)
- [Does CAP apply to microservices?](https://www.youtube.com/watch?v=PgHMtMmSn9s)