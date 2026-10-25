# Agents, Tools, and Workflows

## Scope

Understand the difference between an agent, a tool, and a workflow; autonomy is a design choice.

## Definitions

- A tool performs a bounded operation through a typed interface.
- A workflow defines known steps, conditions, state, and ownership.
- An agent uses a model to select or sequence actions within explicit limits.

## Architect questions

- Can the behavior be implemented deterministically?
- What authority and tools does the agent actually need?
- What prevents loops, unsafe actions, and unbounded cost?
