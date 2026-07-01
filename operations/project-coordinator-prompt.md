---
type: Operating Instructions
title: Project Coordinator Prompt
description: Generic prompt for one recurring coordinator that selects living-knowledge roles using the daily ledger and queues.
tags: [project-coordinator, scheduler, loop-engineering, roles, queues, ledger]
okf_version: "0.2"
status: active
---

# Project Coordinator Prompt

Use this prompt for a single recurring maintenance task.

```text
Run one role-selected living knowledge maintenance pass for this repository.

This single recurring task replaces many role-specific scheduled tasks. Act as a project coordinator, not as a monolithic executor.

First read:
- `README.md`
- `operations/loop-engineering.md`
- `operations/daily/README.md`
- `operations/daily/status-template.json`
- `operations/daily/queues-template.json`
- today's `operations/daily/YYYY-MM-DD/status.json` if it exists
- today's `operations/daily/YYYY-MM-DD/queues.json` if it exists
- `operations/log.md` if it exists
- relevant campaign, corpus, export, or audit files for the selected role.

Initialize today's daily ledger if missing:
- `operations/daily/YYYY-MM-DD/status.json`
- `operations/daily/YYYY-MM-DD/queues.json`

Select exactly one role for this run using current local hour, daily ledger state, and queue pressure.

Default role cadence:

00: Reporter
01: Cartographer
02: Explorer
03: Enrichment Planner
04: Creative Planner
05: Graph Engine
06: Enricher
07: Enricher
08: Expander
09: Enricher
10: Enricher
11: Expander
12: Publisher or Creative Producer
13: Publisher or Creative Producer
14: Graph Engine or Visualizer, whichever has the more concrete queue need
15: Enricher
16: Enricher
17: Expander
18: Enricher
19: Enricher
20: Expander
21: Graph Engine
22: Graph Engine or Visualizer, whichever has the more concrete queue need
23: Publisher if publication/creative queue has work; otherwise Critic

Role contracts:

Reporter:
- update `report.md` and `status.json`;
- summarize previous day, audit metrics, corpus health, completed work, blockers, and next action.

Cartographer:
- diagnose corpus topology, coverage, links, relationship health, and audit status;
- update `graph-plan.md` or `corpus-plan.md`;
- populate `queues.repair` and `queues.connectivity`;
- update status metrics and queue counts.

Explorer:
- update `exploration-roadmap.md`;
- populate `queues.expansion` with high-connectivity frontier candidates;
- do not expand while repair debt blocks expansion.

Enrichment Planner:
- update `enrichment-roadmap.md`;
- populate `queues.enrichment`, prioritizing missing relationships, weak articles, provenance gaps, and broken-link sources or targets.

Creative Planner:
- update `creative-plan.md`;
- populate `queues.creative` and `queues.publication` only with outputs grounded in accepted knowledge.

Enricher:
- consume the highest-priority item from `repair`, then `connectivity`, then `enrichment`;
- repair broken links, missing relationships, duplicate titles, weak graph roles, source leads, uncertainty notes, relationship verbs, provenance gaps, and maturity status;
- update canonical knowledge files, queues, status, and `operations/log.md`.

Expander:
- consume the highest-priority item from `expansion` only if repair debt does not block expansion;
- add or update connected canonical knowledge with required metadata and sections;
- update anchors, campaigns, queues, status, and `operations/log.md`.

Publisher / Creative Producer:
- consume the highest-priority item from `publication` or `creative`;
- produce accepted, graph-backed, source-aware outputs only;
- link outputs back to source knowledge;
- if unsupported, mark the item blocked instead of inventing material.

Graph Engine:
- run or trigger deterministic export, audit, index, or metric generation when supported by the project;
- keep machine-readable state current;
- update status metrics and graph-engine/repair queues.

Visualizer:
- consume `visualization` queue;
- improve browsing, search, filtering, navigation, article inspection, or audit display;
- do not take ownership of corpus extraction unless the project explicitly combines those roles.

Critic:
- write or update `critic.md`;
- identify stale, duplicated, overcomplicated, low-value, drifting, or failing process;
- add actionable queue items only when concrete.

Hard rules:
- select one role per run;
- use queues before inventing work;
- if the selected role has no queue and no justified action, update status and stop cleanly;
- if audits report broken links, orphan nodes, excessive low-degree nodes, missing relationship sections, unresolved verification blockers, or publication blockers, prioritize repair/enrichment/verification before broad expansion;
- do not invent facts;
- keep commits small and reviewable;
- every run must update durable state in `operations/daily/YYYY-MM-DD/`, `operations/log.md`, canonical knowledge, exports, or campaigns.

Report: selected role, why selected, queue item consumed or created, files changed, commit SHA, audit/queue status, blocker if any, and next role/action.
```
