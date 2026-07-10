---
type: Entry Point
title: living-knowledge
description: Runtime-neutral package for governed knowledge maintenance through review cycles, provenance, verification, and publication gates.
tags: [living-knowledge, campaigns, verification, knowledge, provenance, okf]
okf_version: "0.2"
status: draft
---

# living-knowledge

`living-knowledge` defines how a changing knowledge corpus is reviewed, revised, linked, retired, and published over time.

Install it with:

```bash
npx architectonic add living-knowledge
```

## Role

```text
knowledge         = retained claims, sources, evidence, uncertainty, and gaps
living-knowledge  = the maintenance process applied to that corpus
```

A maintenance process may use bounded campaigns, recurring review, source comparison, verification gates, provenance records, publication rules, and explicit retirement decisions.

## Relationship to the ensemble

```text
constitution      = composes the ensemble
doctrine          = governs why and under what rules a corpus changes
identity          = defines who may review, publish, or retire material
project           = provides operating context for a concrete corpus
skills            = provides reusable verification and maintenance procedures
knowledge         = stores the corpus
models            = records model constraints relevant to extraction, synthesis, and retrieval
agents            = may perform delegated maintenance work within explicit permissions
living-knowledge  = coordinates reviewed corpus change
meta              = audits the maintenance process and its revision policy
```

## Maintenance cycle

```text
define a bounded question or gap
inspect candidate sources
compare them with the existing corpus
assess overlap, utility, provenance, uncertainty, and risk
propose additions, revisions, links, or retirements
verify accepted changes
publish reviewed outputs
record evidence and decisions
select the next useful gap
```

## Operating principles

- Canonical source files remain readable without the maintenance runtime.
- Generated indexes, embeddings, graph exports, and summaries remain replaceable.
- Claims retain recoverable provenance.
- Stale, conflicting, weakly sourced, and missing material is reported explicitly.
- Typed relationships supplement source pages rather than replacing them.
- Taxonomies may evolve through versioned schemas and migrations.
- Publication and destructive changes pass through defined review gates.
- Maintenance work is selected by value and evidence rather than by a need to keep processes active.

## Coordination

A corpus may use a scheduler, queue, ledger, or another coordination mechanism. The durable requirement is shared state: independent workers should not create competing queues, duplicate campaigns, or conflicting sources of truth.

```text
observe
select one bounded change
act
verify
record evidence and decisions
repeat when useful
```

Roles are implementation aids. Reporting, source review, graph maintenance, enrichment, publication, and criticism should remain separate only when those distinctions improve accountability.

## Boundary

This package defines maintenance procedures. It should not contain the corpus it maintains. The maintenance process remains domain-neutral; the corpus supplies the subject matter.