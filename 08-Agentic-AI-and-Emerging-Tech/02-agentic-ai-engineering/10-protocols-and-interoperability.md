# Protocols and Interoperability

Protocols standardize communication. They do not automatically provide authentication, authorization, safe tools, or trustworthy agents. Treat every protocol endpoint and remote participant as an integration boundary.

## Model Context Protocol (MCP)

MCP defines a client/server protocol for exposing tools, resources, and prompts to AI applications. The host typically controls user experience and policy; an MCP client connects to one or more servers; servers expose declared capabilities.

Use MCP when multiple applications need a consistent integration contract or tools should be reusable across hosts. A local Python function or internal API may be simpler for a single workflow.

Before enabling an MCP server, review its publisher and code, transport, authentication, authorization scope, data egress, tool side effects, versioning, network access, and auditability. The host should decide which capabilities are available in a given session. Tool descriptions are not a security boundary.

## Agent-to-Agent Handoffs

Agent-to-agent protocols can support capability discovery and task handoff between independently operated agents. Define who owns the task, what data is shared, how the receiver is authenticated, how results are validated, how timeouts and cancellation work, and who is accountable for side effects. Keep handoffs bounded and auditable.

## Contract Checklist

- Protocol and schema version are explicit.
- Caller identity and delegated authority are verified.
- Inputs and outputs are typed, size-limited, and validated.
- Data classification and tenant context survive the handoff.
- Timeout, retry, cancellation, and idempotency semantics are documented.
- Tool permissions are least-privilege and side effects require the proper approval.
- Logs avoid secrets and unnecessary user content while retaining correlation IDs.
- Capability removal and credential revocation can be performed promptly.

## Exercise

Expose a read-only document-search tool through an MCP server. Add an allowlist in the host, tenant-scoped authorization in the server, a response-size cap, an audit record, and tests for unauthorized resource IDs. Then compare it with a direct typed function call and document the operational trade-offs.

Related references: [MCP concepts](../01-agentic-ai/13-model-context-protocol.md), [agent-to-agent protocols](../01-agentic-ai/14-agent-to-agent-protocols.md), and [agent contracts](../01-agentic-ai/16-agent-contracts-and-tool-catalogs.md).