---
type: Entry Point
title: living-knowledge
description: Optional template for governed knowledge maintenance through campaigns, verification, and publication gates.
tags: [living-knowledge, campaigns, verification, knowledge, okf]
okf_version: "0.1"
status: draft
---

# living-knowledge

`living-knowledge` is an optional Architectonic package for governed maintenance of a knowledge corpus.

Install it with:

```bash
npx architectonic add living-knowledge
```

## Role

A living knowledge system maintains a corpus through explicit campaigns, review procedures, verification gates, provenance records, and publication rules.

It is not the same as `knowledge`.

```text
knowledge         = the corpus
living-knowledge  = the maintenance pattern for a corpus
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

## Boundary

This package defines maintenance procedures. It should not contain the corpus it maintains.
