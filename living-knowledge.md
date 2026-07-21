---
type: Living Knowledge
title: Living Knowledge Contract
description: Governed maintenance for frequently changing knowledge corpora.
tags: [living-knowledge, maintenance, verification, publication, provenance]
protocol_version: "0.2.0"
status: experimental
---

# Living Knowledge Contract

`knowledge` is the corpus. `living-knowledge` is an optional maintenance mode applied to a corpus whose sources or claims change frequently.

## Maintenance cycle

```text
define a bounded question or gap
inspect candidate sources
compare them with the current corpus
assess provenance, overlap, utility, uncertainty, staleness, and risk
propose additions, revisions, links, or retirements
verify accepted changes
publish through defined gates
record evidence and decisions
stop or select the next useful gap
```

## Rules

- Canonical corpus files remain readable without the maintenance runtime.
- Discovery and comparison may be automated; publication and destructive changes remain governed.
- Claims retain recoverable provenance.
- Stale, conflicting, weakly sourced, and missing material is reported explicitly.
- Work is selected by value and evidence, not by a need to keep an autonomous loop active.

This layer does not authorize uncontrolled self-mutation.
