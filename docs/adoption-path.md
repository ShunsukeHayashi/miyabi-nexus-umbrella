# Adoption Path

## Who This Is For

Use this guide when you are trying to adopt Miyabi Nexus without overloading a single repository
with every concern.

## Fast Path

1. Read [positioning.md](positioning.md)
   Understand the four layers and decide which layer owns your problem.
2. Read [architecture.md](architecture.md)
   Confirm where code flow, runtime flow, and planning flow intersect.
3. Pick the starting repository
   Use the layer map below to choose the correct implementation surface.

## Layer-by-Layer Entry

### If you need better code graph accuracy

Start with:
- GitNexus upstream
- Miyabi-Nexus only when the change is clearly fork-specific

Typical work:
- symbol resolution
- graph traversal accuracy
- query/context/impact behavior

### If you need safer operations

Start with:
- gitnexus-stable-ops

Typical work:
- runtime pinning
- doctor checks
- reindex safety
- graph freshness and health gates

### If you need better planning before implementation

Start with:
- context-and-impact

Typical work:
- impact-zero sanity checks
- context fusion
- planning guardrails
- fallback behavior when one signal is weak

### If you need to explain or package the system

Start with:
- Miyabi Nexus Umbrella

Typical work:
- external-facing README
- architecture summaries
- adoption paths
- roadmap and backlog framing

## Recommended Adoption Order

1. GitNexus baseline
   Confirm the graph engine and runtime version you trust.
2. StableOps gates
   Make graph freshness and runtime health explicit.
3. Context-and-impact planning
   Fuse code graph, knowledge context, and quality checks.
4. Umbrella docs and launch story
   Present the stack as one understandable product family.

## Rule of Thumb

Do not push planning logic into StableOps.
Do not push runtime policy into context-and-impact.
Do not push portfolio explanation into the core engine repository.
