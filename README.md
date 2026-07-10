---
type: Entry Point
title: living-knowledge
description: Runtime-neutral package for governed knowledge maintenance through review cycles, provenance, verification, and publication gates.
tags: [living-knowledge, campaigns, verification, knowledge, provenance, okf]
okf_version: "0.2"
status: draft
---

# living-knowledge

```bash
npx architectonic add living-knowledge
```

`living-knowledge` defines how a changing knowledge corpus is reviewed, revised, linked, retired, and published over time. It is optional. Add it when `knowledge` alone is not enough because the subject matter changes faster than ordinary manual curation.

## knowledge vs living-knowledge

```text
knowledge         = the corpus: claims, sources, evidence, uncertainty, gaps
living-knowledge  = the maintenance process applied to that corpus
```

Use `knowledge` for any corpus you curate directly.

Add `living-knowledge` when sources change often and the corpus must stay current — for example market data, tax codes, building codes, regulatory filings, security advisories, or provider catalogs. The process is domain-neutral; the corpus supplies the subject matter.

## Autoresearch

Maintenance may run as bounded review cycles or as **autoresearch**: recurring passes that inspect candidate sources, compare them with the existing corpus, and propose updates under explicit review gates.

The pattern is similar in spirit to [Karpathy's autoresearch](https://github.com/karpathy/autoresearch) — propose, measure, keep or discard — applied here to corpus change rather than model training. Search and compare are automated where appropriate; publication and destructive changes pass through defined gates.

Without `living-knowledge`, a `knowledge` corpus remains valid. You maintain it through skills, meta review, and ordinary human judgment.

## In the ensemble

```text
constitution      composition contract for the ensemble
doctrine          purpose, principles, ontology, epistemology, ethics, governance, incentives
identity          actors, roles, authority, delegation, incentives, privacy
project           operating-unit context, sources, decisions, risks, continuity
skills            reusable procedures, verification, failure handling
knowledge         claims, sources, evidence, uncertainty, known unknowns
models            model metadata, evaluations, capability requirements, routing policy
agents            software actors composed from identity, skills, models, knowledge, permissions
living-knowledge  optional: governed maintenance of frequently changing corpora
meta              audit, upkeep, drift review, revision policy
```

## Commands

```bash
npx architectonic add living-knowledge
npx architectonic add living-knowledge --source npm
npx architectonic add knowledge              # corpus layer (required companion)
npx architectonic init
npx architectonic list
npx architectonic doctor
```

CLI: https://github.com/architectonic/architectonic

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
- Publication and destructive changes pass through defined review gates.
- Maintenance work is selected by value and evidence rather than by a need to keep processes active.

## Boundary

This package defines maintenance procedures. It should not contain the corpus it maintains.
