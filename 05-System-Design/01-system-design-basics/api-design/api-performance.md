# API Performance

API performance is the observed cost of serving a request under a defined workload. Start with a measurable user or business target, then optimize the bottleneck shown by production telemetry or a representative load test.

## What to measure

- **Latency:** measure percentiles such as p50, p95, and p99; averages can hide slow requests.
- **Throughput:** record successful requests per second at the expected request mix.
- **Errors and timeouts:** separate client errors, server failures, and dependency failures.
- **Resource saturation:** track CPU, memory, connection pools, queues, and downstream limits.
- **Workload shape:** include concurrency, payload sizes, read/write mix, and traffic bursts.

Write targets with a scope and a measurement window, for example: "p95 read latency below 250 ms at 800 requests per second, with fewer than 0.1% server errors." Treat sample numbers as requirements to validate, not universal targets.

## A practical investigation sequence

1. Establish a baseline with representative traffic and payloads.
2. Trace a slow request across application code and dependencies.
3. Identify whether the bottleneck is computation, network round trips, storage, contention, or a saturated dependency.
4. Change one factor at a time and compare latency percentiles, throughput, and error rates.
5. Re-test at expected peak load and document the new capacity limit.

## API-level improvements

- Reduce unnecessary calls with suitable resource shapes, batching, and pagination.
- Keep payloads bounded; return only fields the client needs and compress responses where appropriate.
- Reuse connections and avoid serial dependency calls when independent work can safely run concurrently.
- Set explicit deadlines and bounded retries so slow dependencies do not consume all request capacity.
- Move work that does not need to finish before the response into an asynchronous workflow.
- Optimize code only after profiling identifies meaningful CPU or allocation cost.

These are investigation options, not defaults: caching can introduce staleness, concurrency can increase downstream load, and retries can amplify an outage.

## Related topics

- [Caching](../caching.md) for cache placement, freshness, and invalidation.
- [Rate limiting](rate-limiting.md) for admission control and overload protection.
- [Scalability](../scalability.md) for capacity growth and scaling approaches.
- [Network protocols and load balancing](../../02-distributed-systems/network-protocols-and-load-balancer.md) for transport and traffic distribution.
- [Observability](../observability.md) for logs, metrics, and traces.
- [Non-functional requirements](../nfrs-for-hld.md) for defining performance targets as part of HLD.
