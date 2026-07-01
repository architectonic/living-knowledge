---
type: Operating Instructions
title: Daily Ledger
description: Shared daily state structure for role-based living knowledge maintenance.
tags: [daily-ledger, loop-engineering, status, queues, roles]
okf_version: "0.2"
status: active
---

# Daily Ledger

## Purpose

The daily ledger is the shared state object for a living knowledge maintenance loop.

It lives under:

```text
operations/daily/YYYY-MM-DD/
```

This prevents hidden-memory dependence and makes maintenance inspectable.

## Required Daily Files

Each day should eventually contain:

```text
status.json
queues.json
report.md
graph-plan.md
exploration-roadmap.md
enrichment-roadmap.md
creative-plan.md
critic.md
```

A project may rename `graph-plan.md` to `corpus-plan.md` when the corpus is not graph-shaped. The role is the same: diagnose structure, coverage, and health.

## `status.json`

Machine-readable daily state. Start from `operations/daily/status-template.json`.

## `queues.json`

Machine-readable work queues. Start from `operations/daily/queues-template.json`.

## Daily Markdown Files

- `report.md`: operational summary and memory.
- `graph-plan.md`: topology, coverage, link, audit, and relationship diagnosis.
- `exploration-roadmap.md`: frontier candidates and growth bridge plan.
- `enrichment-roadmap.md`: existing-article improvement plan.
- `creative-plan.md`: publication and output plan.
- `critic.md`: entropy-control review.

## Role Write Rules

- Reporter updates `report.md` and `status.json`.
- Cartographer updates `graph-plan.md`, `queues.json`, and `status.json`.
- Explorer updates `exploration-roadmap.md` and `queues.json`.
- Enrichment Planner updates `enrichment-roadmap.md` and `queues.json`.
- Creative Planner updates `creative-plan.md` and `queues.json`.
- Enricher consumes `repair`, `connectivity`, and `enrichment` queues.
- Expander consumes `expansion` queue.
- Publisher consumes `publication` and `creative` queues.
- Graph Engine updates exports, indexes, audits, and metrics.
- Visualizer consumes `visualization` queue.
- Critic writes `critic.md` and may add queue items.

## Minimal Daily Initialization

If a role runs and the daily folder does not exist, it may create the folder and initialize `status.json` and `queues.json` from the templates.

## Anti-Noise Rule

Do not create additional daily files unless a recurring role needs them. The daily ledger should reduce coordination noise, not become another uncontrolled document dump.
