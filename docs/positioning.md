# Positioning

## Core idea

Miyabi Nexus is not a single repository.
It is a coordinated stack with separate responsibilities.

This umbrella exists so external readers do not have to infer the structure by reading four
repositories in the correct order.

## Layer model

### 1. GitNexus upstream

Role:
- code graph core
- parser and indexer
- MCP and CLI graph tools

Non-goal:
- business planning context
- production operations policy

### 2. Miyabi-Nexus fork

Role:
- enterprise productization
- custom UI, swarm UX, and product-specific extensions

Non-goal:
- replacing StableOps
- replacing planning orchestration

### 3. gitnexus-stable-ops

Role:
- production operations
- safe reindex
- version pinning
- embedding preservation
- doctor hooks and agent graph

Non-goal:
- owning the full planning pipeline

### 4. context-and-impact

Role:
- pre-implementation planning pipeline
- combine GitNexus code graph, Obsidian context, Context Engineering, and Agent Skill Bus
- produce better decisions before code changes

Non-goal:
- replacing GitNexus core parsing logic
- becoming the operational substrate

## Decision rule

Use this rule when deciding where work belongs:

- graph engine accuracy -> GitNexus upstream or Miyabi-Nexus fork
- runtime safety and operations -> gitnexus-stable-ops
- planning quality, context fusion, fallback logic -> context-and-impact
- cross-repository product explanation -> Miyabi Nexus Umbrella

## Practical reading order

Use this order when onboarding someone new to the stack:

1. Umbrella README
   Get the one-page picture.
2. This positioning document
   Learn the boundaries between layers.
3. Architecture
   Understand data flow, planning flow, and operational flow.
4. Adoption path
   Choose the first repository to enter.
