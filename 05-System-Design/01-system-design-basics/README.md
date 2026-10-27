# System Design Basics

Study system design in decision order: clarify the problem, quantify the workload, define quality targets, analyze failure and trade-offs, then design interfaces and choose architecture.

## Recommended sequence

### 1. Understand the problem and process

1. [What is system design?](what-is-system-design.md)
2. [How to approach HLD](how-to-approach-hld.md)
3. [High-level design process](hld-process.md)
4. [System-design overview](system-design.md)

### 2. Establish requirements and workload

5. [Non-functional requirements](nfrs-for-hld.md)
6. [Capacity estimation](capacity-estimation.md)

### 3. Design for quality attributes

7. [System performance](performance.md)
8. [Scalability](scalability.md)
9. [Availability](availability.md)
10. [Reliability](reliability.md)
11. [Single points of failure](single-points-of-failure.md)
12. [Resilience](resilience.md)
13. [Fault tolerance](fault-tolerance.md)
14. [System-design trade-offs](system-design-trade-offs.md)

### 4. Design API contracts

Continue with the focused [API Design section](api-design/README.md), covering public API guidelines, status codes, errors, performance, and rate limiting.

### 5. Continue to architecture and operations

Use [caching](caching.md) and [observability](observability.md) as cross-cutting design topics. Then study [distributed systems](../02-distributed-systems/README.md), [architecture](../03-architectures/README.md), and [microservices](../04-microservices/README.md), before applying them in [case studies](../../07-Case-Studies-and-Use-Cases/README.md).

The [system-design foundations map](system-design-foundations.md) connects these chapters to data, security, and disaster recovery. External references are collected in the [system-design reading list](reading-list.md). For interview exercises, use the [system-design practice prompts](../../10-Career-and-Interview-Prep/02-interviews/system-design-practice.md).

## Introductory references

- [What is system design?](https://www.youtube.com/watch?v=quLrc3PbuIw)
- [Algorithms to know before system design](https://www.youtube.com/watch?v=xbgzl2maQUU)
- [Single points of failure](https://www.youtube.com/watch?v=-BOysyYErLY)
- [Cloud-native definition from Microsoft](https://learn.microsoft.com/en-us/dotnet/architecture/cloud-native/definition)
- [Cloud-native overview from AWS](https://aws.amazon.com/what-is/cloud-native/)
- [Latency fundamentals from IBM](https://www.ibm.com/topics/latency)
- [System-design mock interview](https://www.youtube.com/watch?v=S1DvEdR0iUo)
- [Designing Amazon Prime Video mock interview](https://www.youtube.com/watch?v=PuU_0esYyhg)
- [Sequence-diagram walkthrough](https://www.youtube.com/watch?v=pCK6prSq8aw)
- [Engineering articles and blogs](https://interviewready.io/blog)
