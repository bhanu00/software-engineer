# E-commerce System Design

A practical design exercise for an online storefront that supports product discovery, checkout, payment, inventory, and order tracking.

## 1. Clarify the requirements

Start by defining the expected traffic, catalog size, regions, availability targets, payment providers, and regulatory constraints.

Functional requirements:

- Browse, search, and filter products.
- Maintain prices, product details, and inventory.
- Manage carts for anonymous and authenticated shoppers.
- Place orders, authorize payment, and track fulfillment.
- Notify customers when order state changes.

Important quality attributes:

- Product browsing should remain available during checkout or downstream outages.
- Checkout must avoid duplicate charges and overselling beyond the agreed inventory policy.
- Catalog reads should be fast, while price and order changes remain auditable.
- Customer and payment data must be protected and access controlled.

## 2. Identify the main components

- **Storefront and API edge:** web/mobile delivery, authentication, routing, and request limits.
- **Catalog service:** product information, categories, and search indexing.
- **Cart service:** short-lived cart state and cart validation.
- **Pricing and promotion service:** current prices, discounts, and tax inputs.
- **Order service:** durable order state and the checkout workflow.
- **Inventory service:** stock visibility, reservations, and release/expiry.
- **Payment adapter:** provider integration, idempotency, and payment status reconciliation.
- **Fulfillment and notification workers:** asynchronous shipment and customer updates.

## 3. Design the checkout flow

1. Validate the cart, customer, address, current price, and promotion eligibility.
2. Create a pending order with a stable idempotency key.
3. Reserve inventory with a bounded reservation expiry.
4. Request payment authorization using the same order identity for provider idempotency.
5. On authorization success, confirm the order and publish an order-confirmed event through a transactional outbox.
6. On failure, cancel the pending order and release inventory; reconcile uncertain provider outcomes before retrying a charge.
7. Fulfillment consumes the confirmed order event and reports shipment progress asynchronously.

The workflow spans independent services, so it is a saga rather than one distributed database transaction. Each step needs an explicit timeout, retry policy, idempotent handler, and compensating action.

## 4. Data and consistency choices

- Keep orders and order-line snapshots in a transactional store so later catalog edits do not rewrite purchase history.
- Store money in an explicit currency and a fixed-precision representation; calculate totals from server-validated prices.
- Use strong coordination for inventory reservation and order transitions where oversell or duplicate payment is unacceptable.
- Treat search indexes, recommendations, and analytics as derived data that can update asynchronously.
- Record state transitions and provider references for audit and reconciliation.

## 5. Failure cases to discuss

- Payment times out after the provider accepted the authorization.
- Inventory reservation succeeds but the order write fails.
- The same checkout request is retried by a browser or gateway.
- An event is delivered more than once or out of order.
- A promotion expires while a cart remains open.
- A downstream fulfillment service is unavailable after order confirmation.

For each case, define the source of truth, retry behavior, customer-visible status, and recovery path.

## 6. Scaling and observability

Scale catalog and search reads independently from order writes. Cache product data with explicit invalidation or bounded staleness, and partition order data only after access patterns and operational costs justify it. Protect checkout dependencies with timeouts, concurrency limits, and load shedding.

Track checkout conversion and latency alongside technical indicators: order creation errors, payment authorization outcomes, inventory reservation conflicts, event lag, and reconciliation backlog. Alert on user-impacting symptoms and test recovery procedures with realistic failure injection.

## Further study

- [System-design basics](../3-System-Design/system-design-basics/README.md)
- [Distributed systems](../3-System-Design/distributed-systems/README.md)
- [Payment platform in AWS](case-study-of-payment-platform-in-aws-cloud.md)
- [Payment system similar to Authorize.net](payment-system-like-authorize.net.md)
- [Case-study collection](system-design-case-studies.md)
