---
type: Operating Instructions
title: Living Knowledge Loop Engineering
description: Reusable single-coordinator, role-based, ledger-driven maintenance loop for any living knowledge corpus.
tags: [living-knowledge, loop-engineering, roles, ledger, queues, state-machine]
okf_version: "0.2"
status: active
---

# Living Knowledge Loop Engineering

## Purpose

A living knowledge system should improve through a governed maintenance loop, not through ad hoc prompts or disconnected recurring jobs.

Canonical loop:

```text
Observe
-> Plan
-> Act
-> Evaluate
-> Repair / Learn
-> Persist memory
-> Repeat
```

## Core Pattern

```text
single project coordinator
many roles
shared ledger
queue-aware execution
```

The coordinator reads durable state, selects exactly one role for the run, works within that role boundary, updates the ledger, and stops.

Time defines when the coordinator may run. Queues define whether meaningful work exists.

## Why One Coordinator

Many independent recurring jobs create drift:

- duplicated plans;
- conflicting priorities;
- stale state;
- role confusion;
- excessive task slots;
- no single account of what happened.

A single coordinator gives the system one heartbeat while preserving specialized roles.

## State Machine

Valid states:

```text
observe
cartography
exploration-planning
enrichment-planning
creative-planning
repair
enrichment
expansion
publication
graph-engine
visualization
critique
reporting
blocked
complete
```

Roles may advance state only after updating durable state files.

## Default Roles

- Reporter: daily memory and operational summary.
- Cartographer: corpus topology, coverage, links, relationship health, and audits.
- Explorer: frontier discovery and growth candidates.
- Enrichment Planner: existing-article improvement priorities.
- Creative Planner: output opportunity selection.
- Enricher: repair, sourcing, article depth, relationship hardening, and maturity promotion.
- Expander: controlled corpus growth.
- Publisher: reviewed outputs grounded in accepted knowledge.
- Graph Engine: deterministic export, audit, index, and metric generation.
- Visualizer: human browsing and comprehension surfaces.
- Critic: entropy control, duplication removal, and process drift review.

## Queue Model

Primary queues:

```text
repair
connectivity
enrichment
expansion
publication
creative
visualization
critic
```

A role should consume queue items before inventing work.

If its queue is empty:

1. verify the empty state;
2. optionally perform one safe opportunistic improvement;
3. update status;
4. stop.

## Priority Rule

Health outranks growth.

If audits report broken links, orphan nodes, missing relationship sections, missing provenance, unresolved verification risk, or publication blockers, the coordinator should prioritize repair, enrichment, verification, and graph-engine work before broad expansion.

Expansion is allowed during repair periods only when it directly resolves a blocking bridge or improves connectivity.

## Durable State Rule

Every run must update at least one durable state surface:

```text
operations/daily/YYYY-MM-DD/
operations/log.md
knowledge/
exports/
campaigns/
```

Concrete projects may rename `knowledge/`, but they should preserve the distinction between canonical knowledge, daily operations, and public exports.

## Evidence Rule

Do not invent facts to satisfy the loop. If evidence is insufficient, mark the queue item blocked or create a verification queue item.

Source notes are required when source uncertainty materially matters, claims are disputed, publication depends on provenance, or a source is being ingested, summarized, or compared.

## Anti-Patterns

Avoid:

- many independent recurring jobs for one corpus;
- one role doing every job;
- expansion while repair debt is blocking;
- disconnected stubs;
- reports that do not alter behavior;
- dashboard redesigns that break deterministic exports;
- provenance-free publication;
- queue items with no concrete action;
- daily files that nobody reads;
- stale process that no role can retire.
