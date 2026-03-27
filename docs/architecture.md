# Architecture

```text
Miyabi Nexus Umbrella
├── GitNexus upstream
│   └── code graph engine
├── Miyabi-Nexus
│   └── enterprise fork and product UX
├── gitnexus-stable-ops
│   └── production operations and agent graph
└── context-and-impact
    └── planning and context-to-execution pipeline
```

## Data flow

1. GitNexus upstream builds and queries the code graph
2. StableOps pins the runtime and keeps the graph healthy in production
3. context-and-impact combines:
   - GitNexus graph
   - Obsidian long-term context
   - Context Engineering quality checks
   - Agent Skill Bus feedback loops
4. The umbrella explains the whole stack and links users to the right layer

## Planning flow

```text
Task request
  -> context-and-impact
    -> GitNexus graph query
    -> Obsidian context lookup
    -> Context Engineering analyze/optimize
    -> planning output
  -> implementation in product or repo layer
```

## Operational flow

```text
Repository change
  -> StableOps doctor / reindex / hooks
  -> GitNexus graph refresh
  -> context-and-impact can trust the graph again
```
