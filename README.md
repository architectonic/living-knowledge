---
type: Entry Point
title: living-knowledge
description: Optional template for governed knowledge maintenance through campaigns, verification, publication gates, and loop-engineered operators.
tags: [living-knowledge, campaigns, verification, knowledge, okf, loop-engineering]
okf_version: "0.2"
status: draft
---

# living-knowledge

`living-knowledge` is an optional Architectonic package for governed maintenance of a knowledge corpus.

Install it with:

```bash
npx architectonic add living-knowledge
```

It is intentionally an addon, not part of the default `constitution` scaffold.

## Role

A living knowledge system maintains a corpus through explicit campaigns, review procedures, verification gates, provenance records, publication rules, and loop-engineered recurring operation.

It is not the same as `knowledge`.

```text
knowledge         = the corpus
living-knowledge  = the maintenance pattern for a corpus
```

## Relationship to the rest of the stack

```text
constitution      = root scaffold
doctrine          = governs why and under what rules the corpus evolves
identity          = defines who may review, publish, or retire material
project           = provides the operating context for a concrete corpus
skills            = provides reusable verification and upkeep procedures
knowledge         = stores the corpus itself
meta              = records system-level upkeep and audit knowledge
living-knowledge  = optional addon that operationalizes corpus maintenance campaigns
```

## Maintenance Cycle

```text
define campaign
inspect candidate sources
compare with existing corpus
assess overlap, utility, provenance, and risk
propose additions, revisions, or retirements
verify accepted changes
publish reviewed outputs
record evidence, cost, and decisions
plan the next campaign
```

## Loop-Engineered Operation

A living knowledge corpus should be maintained by a single project-operator scheduler that selects roles through shared state, not by many independent cron prompts.

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

Operating model:

```text
single project-operator scheduler
many roles
shared daily ledger
queued + scheduled execution
```

The operator reads durable state, chooses exactly one role for the current run, executes that role, updates queues and status, and stops cleanly.

## Default Roles

A cloned living-knowledge system may specialize these roles, but should preserve their boundaries:

- Reporter — daily memory and summary.
- Cartographer — corpus topology, coverage, and link/relationship health.
- Explorer — frontier discovery and candidate growth direction.
- Enrichment Planner — existing-article depth and quality targeting.
- Creative Planner — graph-backed/public-output planning.
- Enricher — repair, deepen, source, and harden existing knowledge.
- Expander — add new connected knowledge only when it can be grounded.
- Publisher — produce reviewed outputs from accepted knowledge.
- Graph Engine — run deterministic exports, audits, metrics, and indexes.
- Visualizer — improve browsing and comprehension surfaces.
- Critic — remove entropy, duplication, stale process, and low-value work.

## Shared Ledger

The reusable ledger contract lives in:

```text
operations/daily/README.md
operations/daily/status-template.json
operations/daily/queues-template.json
```

Each concrete day should instantiate:

```text
operations/daily/YYYY-MM-DD/status.json
operations/daily/YYYY-MM-DD/queues.json
operations/daily/YYYY-MM-DD/report.md
operations/daily/YYYY-MM-DD/graph-plan.md
operations/daily/YYYY-MM-DD/exploration-roadmap.md
operations/daily/YYYY-MM-DD/enrichment-roadmap.md
operations/daily/YYYY-MM-DD/creative-plan.md
operations/daily/YYYY-MM-DD/critic.md
```

## Boundary

This package defines maintenance procedures. It should not contain the corpus it maintains.

A clone may use this package to maintain any topic-specific corpus: philosophy, architecture, biology, law, finance, design systems, company knowledge, research notes, or a total knowledge graph. The loop should stay generic; the corpus supplies the domain.