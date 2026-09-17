# System Design Case Studies

Use these case studies to practice turning a familiar product into requirements, estimates, architecture, trade-offs, data flows, reliability mechanisms, and operational decisions.

For every case study, start by writing functional and non-functional requirements. Then identify the highest-risk component, propose alternatives, and explain the trade-offs before drawing the final architecture.

## Product and Platform Case Studies

1. [How Twitter Timeline Works](https://lnkd.in/eniXMPfU)
2. [How WhatsApp Works](https://lnkd.in/eU2fswMi)
3. [How YouTube Works](https://lnkd.in/e7q9F4Sg)
4. [How Uber Computes ETA](https://lnkd.in/eVKV2ePC)
5. [How Instagram Works](https://lnkd.in/ejBKTZPD)
6. [How Airbnb Works](https://lnkd.in/dGVfstQM)
7. [How Redis Is Used at Scale](https://lnkd.in/ekJMjMG3)
8. [How Spotify Works](https://lnkd.in/eGbWVeNW)
9. [How Tinder Works](https://lnkd.in/en65fv-W)
10. [How Zoom Works](https://lnkd.in/edidhxZw)
11. [How Figma Scaled Postgres to 4M Users](https://lnkd.in/e7De898X)
12. [How Cloudflare Scaled Postgres](https://lnkd.in/eEQP6Apw)
13. [How PayPal Implements the Actor Model](https://lnkd.in/eqcb7MpP)
14. [How Lyft Works](https://lnkd.in/eMTEFyja)
15. [How Bluesky Works](https://lnkd.in/eEhB8V_k)

## Additional Cases to Practice

These are high-value complements to the list above. Use the handbook to develop the design yourself before looking for a reference solution.

1. **URL shortener** — IDs, redirects, caching, abuse prevention, and analytics.
2. **Collaborative document editor** — real-time synchronization, conflict resolution, presence, and offline edits.
3. **Notification platform** — fan-out, user preferences, channels, retries, deduplication, and delivery tracking.
4. **E-commerce checkout and inventory** — reservations, payments, consistency, idempotency, and compensating actions.
5. **Web crawler and search index** — distributed scheduling, politeness, deduplication, storage, ranking, and freshness.
6. **File-sync platform** — chunking, metadata, conflict resolution, large-file transfers, and access control.

## Practice Template

For each design, record:

1. Users, user journeys, and functional requirements.
2. Scale assumptions and non-functional requirements.
3. APIs, data model, and core request/event flow.
4. Architecture choices and alternatives rejected.
5. Consistency, caching, asynchronous processing, and failure handling.
6. Security, privacy, cost, observability, and rollout considerations.

Related reading: [System Design](../system-designs/README.md), [Distributed Systems](../distributed-systems/README.md), [Databases](../database/README.md), and [Architecture](../architectures/README.md).

