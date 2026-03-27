# Miyabi Nexus Umbrella

Docs-first umbrella project for the Miyabi Nexus stack.

This repository does not replace GitNexus core, StableOps, or context-and-impact.
It exists to explain how they fit together, how to adopt them, and how to plan work across them.

## Positioning

The stack has four layers:

1. GitNexus upstream
   The code graph engine: parsing, indexing, symbol graph, `query/context/impact/cypher`.
2. Miyabi-Nexus fork
   Enterprise product and UX extensions on top of GitNexus core.
3. gitnexus-stable-ops
   Operational layer for version pinning, reindex safety, health checks, hooks, and agent graph.
4. context-and-impact
   Planning pipeline that combines GitNexus, Obsidian, Context Engineering, and Agent Skill Bus.

## Why this repository exists

Without an umbrella, the stack is hard to understand from the outside:

- GitNexus upstream looks like the whole product, but it is only the graph core
- StableOps looks like a wrapper, but it is actually the production operations layer
- context-and-impact looks like a single skill, but it is really the planning and execution pipeline

This repository is the single entry point that explains the whole system.

## Repository Map

- [Positioning](docs/positioning.md)
- [Architecture](docs/architecture.md)
- [Roadmap](docs/roadmap.md)
- [Sprint 0](docs/web-sprint-0.md)

## Linked Repositories

- GitNexus upstream: https://github.com/abhigyanpatwari/GitNexus
- Miyabi-Nexus fork: https://github.com/ShunsukeHayashi/Miyabi-Nexus
- StableOps: https://github.com/ShunsukeHayashi/gitnexus-stable-ops
- Context & Impact: https://github.com/ShunsukeHayashi/context-and-impact

## Initial Goal

Sprint 0 focuses on three outcomes:

1. make the positioning understandable from one URL
2. make the integration points explicit
3. turn the integration work into a web-managed backlog
