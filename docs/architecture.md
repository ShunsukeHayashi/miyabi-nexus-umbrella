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

## Responsibility Map

| Layer | Owns | Does not own |
| --- | --- | --- |
| GitNexus upstream | parsing, indexing, symbol graph, graph queries | business planning context, ops policy |
| Miyabi-Nexus | product-specific extensions, enterprise UX, fork-side features | runtime substrate, portfolio explanation |
| gitnexus-stable-ops | runtime pinning, doctor checks, reindex safety, agent graph | full planning orchestration |
| context-and-impact | context fusion, planning guardrails, fallback policy, pre-implementation decisions | core graph parsing, runtime substrate |
| Miyabi Nexus Umbrella | cross-repo explanation, adoption path, roadmap, backlog framing | low-level implementation logic |

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

## Ownership Decision Matrix

When work appears, assign it using this matrix.

| Work type | Primary layer | Secondary layer |
| --- | --- | --- |
| Improve symbol lookup or impact traversal | GitNexus upstream | Miyabi-Nexus |
| Fork-specific UX or enterprise workflow | Miyabi-Nexus | Umbrella for docs |
| Runtime health gate or reindex safety | gitnexus-stable-ops | Umbrella for docs |
| Planning guard, sanity check, context fusion | context-and-impact | gitnexus-stable-ops if runtime state matters |
| Product narrative, adoption docs, roadmap | Miyabi Nexus Umbrella | context-and-impact for planning examples |

## Operational flow

```text
Repository change
  -> StableOps doctor / reindex / hooks
  -> GitNexus graph refresh
  -> context-and-impact can trust the graph again
```

## Integration Principle

The stack should be integrated at the product level, not collapsed into one repository.
Core, ops, and planning remain independent so each layer can improve without blurring ownership.
