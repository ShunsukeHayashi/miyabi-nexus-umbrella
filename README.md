# Miyabi Nexus Umbrella

Docs-first umbrella project for the Miyabi Nexus stack.

This repository is the public entry point for the stack. It does not replace GitNexus core,
StableOps, or context-and-impact. It explains how they fit together, where work belongs, and
how to adopt the full stack without collapsing everything into one repository.

## What Miyabi Nexus Is

Miyabi Nexus is a four-layer stack:

1. GitNexus upstream
   The code graph engine: parsing, indexing, symbol graph, `query/context/impact/cypher`.
2. Miyabi-Nexus fork
   Product-facing fork for enterprise UX and product-specific extensions.
3. gitnexus-stable-ops
   Operations layer for runtime pinning, reindex safety, health checks, hooks, and agent graph.
4. context-and-impact
   Planning pipeline that combines GitNexus, Obsidian, Context Engineering, and Agent Skill Bus.

## Why This Repository Exists

Without an umbrella, the stack is easy to misread:

- GitNexus upstream looks like the whole product, but it is only the graph core
- Miyabi-Nexus looks like the only fork worth reading, but it is not the runtime or planning layer
- StableOps looks like a helper wrapper, but it is the operational substrate
- context-and-impact looks like a single skill, but it is the planning and context-to-execution pipeline

This repository makes the full system understandable from one URL.

## Start Here

Choose the entry point based on what you are trying to solve.

| Goal | Start here | Why |
| --- | --- | --- |
| Understand the whole stack | [docs/positioning.md](docs/positioning.md) | Defines the four layers and decision rules |
| Decide where a new feature belongs | [docs/architecture.md](docs/architecture.md) | Shows responsibility boundaries and flows |
| Plan adoption or rollout | [docs/adoption-path.md](docs/adoption-path.md) | Gives step-by-step entry paths |
| See current priorities | [docs/roadmap.md](docs/roadmap.md) | Tracks sprint-level direction |
| Follow the current sprint | [docs/web-sprint-0.md](docs/web-sprint-0.md) | Maps the web backlog for Sprint 0 |

## Repository Map

- [Positioning](docs/positioning.md)
- [Architecture](docs/architecture.md)
- [Adoption Path](docs/adoption-path.md)
- [Roadmap](docs/roadmap.md)
- [Sprint 0](docs/web-sprint-0.md)

## Linked Repositories

| Layer | Repository | Purpose |
| --- | --- | --- |
| Core engine | https://github.com/abhigyanpatwari/GitNexus | Code graph engine and MCP/CLI graph tools |
| Product fork | https://github.com/ShunsukeHayashi/Miyabi-Nexus | Enterprise fork and product extensions |
| Ops layer | https://github.com/ShunsukeHayashi/gitnexus-stable-ops | Runtime safety, health, pinning, and agent operations |
| Planning layer | https://github.com/ShunsukeHayashi/context-and-impact | Context fusion and planning pipeline |

## Decision Rule

When a task appears, route it like this:

- graph engine accuracy, parser behavior, graph traversal -> GitNexus upstream or Miyabi-Nexus
- runtime safety, doctor checks, pinned versions, graph freshness -> gitnexus-stable-ops
- planning quality, fallback logic, context fusion, decision outputs -> context-and-impact
- cross-repository explanation, positioning, adoption, portfolio narrative -> Miyabi Nexus Umbrella

## Initial Goal

Sprint 0 focuses on three outcomes:

1. make the positioning understandable from one URL
2. make the integration points explicit
3. turn the integration work into a web-managed backlog
