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
select one dependency-clear item from the project work ledger
confirm its bounded question or gap
inspect candidate sources
compare them with the current corpus
assess provenance, overlap, utility, uncertainty, staleness, and risk
propose additions, revisions, links, or retirements
verify accepted changes
publish through defined gates
record evidence and the resulting ledger transition
stop or select the next useful gap
```

## Rules

- Canonical corpus files remain readable without the maintenance runtime.
- Discovery and comparison may be automated; publication and destructive changes remain governed.
- Claims retain recoverable provenance.
- Stale, conflicting, weakly sourced, and missing material is reported explicitly.
- Work is selected by value and evidence, not by a need to keep an autonomous loop active.
- Backlog, queue, now, reports, and dashboards are views over the one work ledger, never additional work authorities.
- An empty ready queue is a clean stop; a scheduler wake does not justify invented maintenance.

This layer does not authorize uncontrolled self-mutation.
