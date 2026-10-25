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
| Move toward AI Architect or AI engineering leadership | [Agentic AI learning roadmap](8-Agentic-AI-and-Emerging-Tech/1-agentic-ai/agentic-ai-learning-roadmap.md) |
| Prepare for interviews | [Path E: Interview Preparation](#path-e-interview-preparation) |

## Core Sequence

```text
Programming and OOP -> Databases -> Security -> Cloud and DevOps -> System Design ->
Advanced Topics -> Case Studies -> Emerging Tech (optional) -> Solutions -> Career and Interview Prep
```

## Path A: Programming to Senior Engineer

Estimated pace: 12 to 16 weeks.

### Phase 1: Programming fundamentals

1. Review the [programming and OOP guide](1-Programming-and-OOP/README.md).
2. Study [.NET and C# fundamentals](1-Programming-and-OOP/4-dotnet/README.md) if C# is your primary language.

Outcome: you can read and write small programs and explain basic object-oriented concepts.

### Phase 2: Data structures and algorithms

Follow the [DSA section](1-Programming-and-OOP/1-dsa/README.md), starting with complexity, arrays, strings, linked lists, trees, and recursion. Review the [mathematical formulas](1-Programming-and-OOP/1-dsa/math-formulas.md) as needed, practice using the [problem-solving interview notes](10-Career-and-Interview-Prep/2-interviews/problem-solving.md), then cover DFS, dynamic programming, greedy algorithms, and the pattern files.

Outcome: you can recognize common problem patterns and solve medium-level coding problems with clear complexity analysis.

### Phase 3: Object-oriented design

Follow the [Object-Oriented Design section](1-Programming-and-OOP/2-oops/README.md), starting with [low-level design principles](1-Programming-and-OOP/2-oops/low-level-design-principles.md) and continuing through patterns and case studies.

Outcome: you can model a small domain, apply patterns for a reason, and explain alternatives.

### Phase 4: Application development

Use [.NET and frontend](1-Programming-and-OOP/4-dotnet/README.md) or [Backend development](1-Programming-and-OOP/3-backend-development/README.md) for technology-specific depth, then implement or modify a sample in [Solutions and POCs](9-Solutions-and-POCs/README.md).

Outcome: you can turn a design into a working, tested application.

## Path B: System Design and Distributed Systems

Estimated pace: 12 to 16 weeks. Start after you are comfortable with basic APIs, databases, and programming.

### Phase 1: System-design foundations

1. [System-design foundations](5-System-Design/1-system-design-basics/system-design-foundations.md)
2. [System Design section](5-System-Design/1-system-design-basics/README.md)
3. [Non-functional requirements](6-Advanced-Topics/nfrs-for-hld.md)
4. [High-level design process](5-System-Design/1-system-design-basics/hld-process.md)
5. [System-design trade-offs](5-System-Design/1-system-design-basics/system-design-trade-offs.md)

### Phase 2: Performance, APIs, and data

1. [Scalability](5-System-Design/1-system-design-basics/scalability.md)
2. [API performance](6-Advanced-Topics/api-performance.md)
3. [Caching](6-Advanced-Topics/caching.md)
4. [Rate limiting](6-Advanced-Topics/rate-limiting.md)
5. [Databases and Data Systems](2-Databases-and-Data/README.md)
6. [API guidelines](5-System-Design/1-system-design-basics/public-api-guidelines.md)

### Phase 3: Distributed systems

Follow [Distributed Systems](5-System-Design/2-distributed-systems/README.md), then read [network protocols and load balancing](6-Advanced-Topics/network-protocols-and-load-balancer.md).

### Phase 4: Architecture and events

1. [Architecture](5-System-Design/3-architectures/README.md)
2. [Event sourcing and materialized views](5-System-Design/2-distributed-systems/event-sourcing-materialized-view.md)
3. [Event non-delivery](5-System-Design/2-distributed-systems/event-non-delivery.md)
4. [Background jobs](5-System-Design/2-distributed-systems/background-jobs.md)
5. [Batch versus stream processing](5-System-Design/2-distributed-systems/batch-vs-stream-processing.md)

Outcome: you can lead an end-to-end design discussion, defend its trade-offs, and explain how it behaves when dependencies fail.

### Phase 5: Advanced topics and case studies

1. Review the [advanced topics](6-Advanced-Topics/README.md), including performance, caching, rate limiting, and observability.
2. Work through the [case studies](7-Case-Studies-and-Use-Cases/README.md) and explain the requirements, architecture, trade-offs, and failure modes.
3. Build or extend a relevant project from [Solutions and POCs](9-Solutions-and-POCs/README.md).

Outcome: you can apply design principles to a concrete problem and defend the resulting choices.

## Path C: Cloud Platform and Reliability

Estimated pace: 6 to 10 weeks.

1. [DevOps and Operations](4-Cloud-and-DevOps/1-devops/README.md)
2. [GitOps](4-Cloud-and-DevOps/2-gitops/README.md)
3. [Container fundamentals](1-Programming-and-OOP/4-dotnet/container-fundamentals.md)
4. [Cloud monitoring](4-Cloud-and-DevOps/1-devops/monitoring-cloud-based.md)
5. [Operational excellence](4-Cloud-and-DevOps/1-devops/operational-excellence.md)
6. [Disaster recovery](4-Cloud-and-DevOps/1-devops/disaster-recovery.md)
7. [Security](3-Security/README.md)
8. [Cascading failures](5-System-Design/2-distributed-systems/cascading-failure.md)
9. [Resiliency versus fault tolerance](5-System-Design/2-distributed-systems/resiliency-vs-fault-tolerance.md)

Apply this work to the GitOps sample or another POC in [Solutions](9-Solutions-and-POCs/README.md): add health checks, structured logs, metrics, a deployment pipeline, and a failure-mode test.

Outcome: you can design, deploy, observe, and operate a service rather than only implement one.

## Path D: Staff and Principal Engineer

Estimated pace: ongoing; spend 12 focused weeks preparing before interviews.

Use [Career Preparation](10-Career-and-Interview-Prep/1-career/README.md) as the role-requirements source of truth, then track progress in the [target-role competency matrix](10-Career-and-Interview-Prep/1-career/target-role-competency-matrix.md).

### Technical depth

1. Complete [Path B](#path-b-system-design-and-distributed-systems) and [Path C](#path-c-cloud-platform-and-reliability).
2. Study [System Design](5-System-Design/1-system-design-basics/README.md), [Architecture](5-System-Design/3-architectures/README.md), [Distributed Systems](5-System-Design/2-distributed-systems/README.md), and [Use Cases](7-Case-Studies-and-Use-Cases/README.md) as design-review exercises.
3. Build one portfolio-quality system in [Solutions](9-Solutions-and-POCs/README.md), with a design document, ADRs, load tests, SLOs, dashboards, and a cost/reliability analysis.
4. Review [Agentic AI](8-Agentic-AI-and-Emerging-Tech/1-agentic-ai/README.md) for modern system concerns.
5. Follow the [Agentic AI learning roadmap](8-Agentic-AI-and-Emerging-Tech/1-agentic-ai/agentic-ai-learning-roadmap.md), including its platform, governance, product, and leadership stages.

### Leadership depth

1. Read [Senior engineer interview preparation](10-Career-and-Interview-Prep/2-interviews/senior-engineer.md).
2. Write 10 career stories using: context, constraints, alternatives, decision, alignment, result, and learning.
3. Practice explaining architecture to three audiences: an engineer, a product leader, and an executive.
4. Turn one POC into a multi-team style proposal: roadmap, migration plan, risks, ownership boundaries, and success metrics.

Outcome: you can demonstrate technical judgment and organizational impact, not only individual coding ability.

## Path E: Interview Preparation

Estimated pace: 6 to 8 weeks; run it alongside the relevant technical path.

1. Follow [Interview Preparation](10-Career-and-Interview-Prep/2-interviews/README.md).
2. Revisit [DSA](1-Programming-and-OOP/1-dsa/README.md) for coding rounds.
3. Use [System Design](5-System-Design/1-system-design-basics/README.md) and [Use Cases](7-Case-Studies-and-Use-Cases/README.md) for design rounds.
4. Practice company-focused material in [Interviews](10-Career-and-Interview-Prep/2-interviews/README.md).
5. Use [modernization mock interviews](10-Career-and-Interview-Prep/2-interviews/my-modernization-mock-interviews.md) to rehearse communication and migration trade-offs.

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
