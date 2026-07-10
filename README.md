---
type: Entry Point
title: living-knowledge
description: Optional template for governed knowledge maintenance through campaigns, verification, publication gates, and recurring review.
tags: [living-knowledge, campaigns, verification, knowledge, provenance, okf]
okf_version: "0.2"
status: draft
---

# living-knowledge

`living-knowledge` is an optional Architectonic package for maintaining a knowledge corpus through explicit review cycles.

Install it with:

```bash
npx architectonic add living-knowledge
```

It is intentionally an addon, not part of the default `constitution` scaffold.

## Role

A living knowledge system maintains a corpus through explicit campaigns, review procedures, verification gates, provenance records, publication rules, and recurring operation.

It is not the same as `knowledge`.

```text
knowledge         = the corpus
living-knowledge  = the maintenance pattern for a corpus
```

## Relationship to the rest of the stack

```text
constitution      = root scaffold
doctrine          = governs why and under what rules the corpus changes
identity          = defines who may review, publish, or retire material
project           = provides the operating context for a concrete corpus
skills            = provides reusable verification and upkeep procedures
knowledge         = stores the corpus itself
meta              = records system-level upkeep and audit knowledge
living-knowledge  = coordinates corpus maintenance campaigns
```

## Maintenance cycle

```text
define a bounded campaign
inspect candidate sources
compare them with the existing corpus
assess overlap, utility, provenance, uncertainty, and risk
propose additions, revisions, links, or retirements
verify accepted changes
publish reviewed outputs
record evidence and decisions
review the next highest-value gap
```

## Operating principles

- Canonical source files remain readable without the maintenance runtime.
- Generated indexes, embeddings, graph exports, and summaries remain replaceable.
- Claims retain recoverable provenance.
- Stale, conflicting, weakly sourced, and missing material is reported explicitly.
- Typed relationships supplement source pages; they do not replace them.
- Taxonomies may evolve through versioned schemas and migrations.
- Publication and destructive changes pass through defined human or delegated review gates.
- Maintenance work is selected by value and evidence, not by a need to keep every role busy.

## Recurring operation

A corpus may use one scheduler or another coordination mechanism. The important constraint is shared durable state: independent workers should not create competing queues, duplicate campaigns, or conflicting sources of truth.

A minimal recurring loop is:

```text
observe
plan one bounded change
act
verify
record evidence and decisions
repeat when useful
```

Roles are optional implementation aids. A corpus may distinguish reporting, source review, graph maintenance, enrichment, publication, and criticism when those boundaries improve accountability. It should not create permanent roles or artifacts without recurring work to justify them.

## Shared state

A concrete implementation may maintain a dated ledger containing status, queues, reports, and review evidence. Templates in `operations/daily/` provide one possible shape; they are not required ontology.

## Boundary

This package defines maintenance procedures. It should not contain the corpus it maintains.

A clone may use this package to maintain any topic-specific corpus. The maintenance pattern should stay domain-neutral; the corpus supplies the subject matter.
