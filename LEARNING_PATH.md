# Learning Path

This is the guided route through the Software Engineering Handbook. Use the [book index](INDEX.md) whenever you want to explore beyond the suggested sequence.

The path is intentionally flexible: finish each outcome, rather than treating the time estimates as a deadline.

## Choose Your Starting Point

| Your goal | Start here |
| --- | --- |
| Build programming and interview fundamentals | [Path A: Programming to Senior Engineer](#path-a-programming-to-senior-engineer) |
| Improve system-design ability | [Path B: System Design and Distributed Systems](#path-b-system-design-and-distributed-systems) |
| Become stronger in cloud/platform engineering | [Path C: Cloud Platform and Reliability](#path-c-cloud-platform-and-reliability) |
| Prepare for Staff, Principal, or PMTS roles | [Path D: Staff and Principal Engineer](#path-d-staff-and-principal-engineer) |
| Move toward AI Architect or AI engineering leadership | [Agentic AI learning roadmap](08-Agentic-AI-and-Emerging-Tech/01-agentic-ai/agentic-ai-learning-roadmap.md) |
| Prepare for interviews | [Path E: Interview Preparation](#path-e-interview-preparation) |

## Core Sequence

```text
Programming and OOP -> Databases -> Security -> Cloud and DevOps -> System Design ->
Advanced Topics -> Case Studies -> Emerging Tech (optional) -> Solutions -> Career and Interview Prep
```

## Path A: Programming to Senior Engineer

Estimated pace: 12 to 16 weeks.

### Phase 1: Programming fundamentals

1. Review the [programming and OOP guide](01-Programming-and-OOP/README.md).
2. Study [.NET and C# fundamentals](01-Programming-and-OOP/04-dotnet/README.md) if C# is your primary language.

Outcome: you can read and write small programs and explain basic object-oriented concepts.

### Phase 2: Data structures and algorithms

Follow the [DSA section](01-Programming-and-OOP/01-dsa/README.md), starting with complexity, arrays, strings, linked lists, trees, and recursion. Review the [mathematical formulas](01-Programming-and-OOP/01-dsa/math-formulas.md) as needed, practice using the [problem-solving interview notes](10-Career-and-Interview-Prep/02-interviews/problem-solving.md), then cover DFS, dynamic programming, greedy algorithms, and the pattern files.

Outcome: you can recognize common problem patterns and solve medium-level coding problems with clear complexity analysis.

### Phase 3: Object-oriented design

Follow the [Object-Oriented Design section](01-Programming-and-OOP/02-oops/README.md), starting with [low-level design principles](01-Programming-and-OOP/02-oops/low-level-design-principles.md) and continuing through patterns and case studies.

Outcome: you can model a small domain, apply patterns for a reason, and explain alternatives.

### Phase 4: Application development

Use [.NET and frontend](01-Programming-and-OOP/04-dotnet/README.md) or [Backend development](01-Programming-and-OOP/03-backend-development/README.md) for technology-specific depth, then implement or modify a sample in [Solutions and POCs](09-Solutions-and-POCs/README.md).

Outcome: you can turn a design into a working, tested application.

## Path B: System Design and Distributed Systems

Estimated pace: 12 to 16 weeks. Start after you are comfortable with basic APIs, databases, and programming.

### Phase 1: System-design foundations

1. [What is system design?](05-System-Design/01-system-design-basics/what-is-system-design.md)
2. [How to approach HLD](05-System-Design/01-system-design-basics/how-to-approach-hld.md)
3. [High-level design process](05-System-Design/01-system-design-basics/hld-process.md)
4. [Non-functional requirements](05-System-Design/01-system-design-basics/nfrs-for-hld.md)
5. [Capacity estimation](05-System-Design/01-system-design-basics/capacity-estimation.md)

### Phase 2: Quality attributes and failure modes

1. [System performance](05-System-Design/01-system-design-basics/performance.md)
2. [Scalability](05-System-Design/01-system-design-basics/scalability.md)
3. [Availability](05-System-Design/01-system-design-basics/availability.md)
4. [Reliability](05-System-Design/01-system-design-basics/reliability.md)
5. [Single points of failure](05-System-Design/01-system-design-basics/single-points-of-failure.md)
6. [Resilience](05-System-Design/01-system-design-basics/resilience.md)
7. [Fault tolerance](05-System-Design/01-system-design-basics/fault-tolerance.md)
8. [System-design trade-offs](05-System-Design/01-system-design-basics/system-design-trade-offs.md)
9. [Caching](05-System-Design/01-system-design-basics/caching.md)

### Phase 3: API design

1. Follow [API design and contract basics](05-System-Design/01-system-design-basics/api-design/README.md).
2. Study [API performance](05-System-Design/01-system-design-basics/api-design/api-performance.md) against the performance targets defined in Phase 1.
3. Apply [rate limiting](05-System-Design/01-system-design-basics/api-design/rate-limiting.md) as an API admission-control mechanism.

### Phase 4: Distributed systems

Follow [Distributed Systems](05-System-Design/02-distributed-systems/README.md), including [network protocols and load balancing](05-System-Design/02-distributed-systems/network-protocols-and-load-balancer.md).

### Phase 5: Architecture and events

1. [Architecture](05-System-Design/03-architectures/README.md)
2. [Event sourcing and materialized views](05-System-Design/02-distributed-systems/event-sourcing-materialized-view.md)
3. [Event non-delivery](05-System-Design/02-distributed-systems/event-non-delivery.md)
4. [Background jobs](05-System-Design/02-distributed-systems/background-jobs.md)
5. [Batch versus stream processing](05-System-Design/02-distributed-systems/batch-vs-stream-processing.md)

Outcome: you can lead an end-to-end design discussion, defend its trade-offs, and explain how it behaves when dependencies fail.

### Phase 6: Observability and case studies

1. Study [observability](05-System-Design/01-system-design-basics/observability.md) and revisit the focused topics from the [System Design index](05-System-Design/README.md).
2. Work through the [case studies](07-Case-Studies-and-Use-Cases/README.md) and explain the requirements, architecture, trade-offs, and failure modes.
3. Build or extend a relevant project from [Solutions and POCs](09-Solutions-and-POCs/README.md).

Outcome: you can apply design principles to a concrete problem and defend the resulting choices.

## Path C: Cloud Platform and Reliability

Estimated pace: 6 to 10 weeks.

1. [DevOps and Operations](04-Cloud-and-DevOps/01-devops/README.md)
2. [GitOps](04-Cloud-and-DevOps/02-gitops/README.md)
3. [Container fundamentals](01-Programming-and-OOP/04-dotnet/container-fundamentals.md)
4. [Cloud monitoring](04-Cloud-and-DevOps/01-devops/monitoring-cloud-based.md)
5. [Operational excellence](04-Cloud-and-DevOps/01-devops/operational-excellence.md)
6. [Disaster recovery](04-Cloud-and-DevOps/01-devops/disaster-recovery.md)
7. [Security](03-Security/README.md)
8. [Cascading failures](05-System-Design/02-distributed-systems/cascading-failure.md)
9. [Resiliency versus fault tolerance](05-System-Design/02-distributed-systems/resiliency-vs-fault-tolerance.md)

Apply this work to the GitOps sample or another POC in [Solutions](09-Solutions-and-POCs/README.md): add health checks, structured logs, metrics, a deployment pipeline, and a failure-mode test.

Outcome: you can design, deploy, observe, and operate a service rather than only implement one.

## Path D: Staff and Principal Engineer

Estimated pace: ongoing; spend 12 focused weeks preparing before interviews.

Use [Career Preparation](10-Career-and-Interview-Prep/01-career/README.md) as the role-requirements source of truth, then track progress in the [target-role competency matrix](10-Career-and-Interview-Prep/01-career/target-role-competency-matrix.md).

### Technical depth

1. Complete [Path B](#path-b-system-design-and-distributed-systems) and [Path C](#path-c-cloud-platform-and-reliability).
2. Study [System Design](05-System-Design/01-system-design-basics/README.md), [Architecture](05-System-Design/03-architectures/README.md), [Distributed Systems](05-System-Design/02-distributed-systems/README.md), and [Use Cases](07-Case-Studies-and-Use-Cases/README.md) as design-review exercises.
3. Build one portfolio-quality system in [Solutions](09-Solutions-and-POCs/README.md), with a design document, ADRs, load tests, SLOs, dashboards, and a cost/reliability analysis.
4. Review [Agentic AI](08-Agentic-AI-and-Emerging-Tech/01-agentic-ai/README.md) for modern system concerns.
5. Follow the [Agentic AI learning roadmap](08-Agentic-AI-and-Emerging-Tech/01-agentic-ai/agentic-ai-learning-roadmap.md), including its platform, governance, product, and leadership stages.
6. Follow the [Enterprise Agentic AI Engineering track](08-Agentic-AI-and-Emerging-Tech/02-agentic-ai-engineering/README.md) through RAG, orchestration, security, evaluation, operations, and the technical capstone.

### Leadership depth

1. Read [Senior engineer interview preparation](10-Career-and-Interview-Prep/02-interviews/senior-engineer.md).
2. Write 10 career stories using: context, constraints, alternatives, decision, alignment, result, and learning.
3. Practice explaining architecture to three audiences: an engineer, a product leader, and an executive.
4. Turn one POC into a multi-team style proposal: roadmap, migration plan, risks, ownership boundaries, and success metrics.

Outcome: you can demonstrate technical judgment and organizational impact, not only individual coding ability.

## Path E: Interview Preparation

Estimated pace: 6 to 8 weeks; run it alongside the relevant technical path.

1. Follow [Interview Preparation](10-Career-and-Interview-Prep/02-interviews/README.md).
2. Revisit [DSA](01-Programming-and-OOP/01-dsa/README.md) for coding rounds.
3. Use [System Design](05-System-Design/01-system-design-basics/README.md) and [Use Cases](07-Case-Studies-and-Use-Cases/README.md) for design rounds.
4. Practice company-focused material in [Interviews](10-Career-and-Interview-Prep/02-interviews/README.md).
5. Use [modernization mock interviews](10-Career-and-Interview-Prep/02-interviews/my-modernization-mock-interviews.md) to rehearse communication and migration trade-offs.

Weekly cadence:

- Two coding sessions
- Two system-design sessions
- One behavioral or leadership mock
- One design-document review or implementation improvement

## Progress Checklist

- [ ] I can solve common DSA patterns and communicate complexity.
- [ ] I can model a domain and justify object-oriented design decisions.
- [ ] I can design an API, data model, cache, and asynchronous workflow.
- [ ] I can explain consistency, retries, idempotency, and failure handling.
- [ ] I can deploy, monitor, and operate a service.
- [ ] I can articulate security and reliability trade-offs.
- [ ] I have one end-to-end POC or application I can discuss deeply.
- [ ] I have evidence-based stories of technical leadership and influence.

## Continue Exploring

The [book index](INDEX.md) is the complete topic map. Use it to find focused references, extra practice material, and adjacent topics after completing a path.
