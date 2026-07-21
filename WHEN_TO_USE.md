# When to Use Living Knowledge

## Use it when

A source changes independently of the local corpus and those changes can invalidate current conclusions.

Examples:

- law, regulation, and building codes;
- market and provider catalogs;
- security advisories;
- product or API documentation with frequent releases;
- operational inventories synchronized from external systems.

## Do not use it when

- updates happen only when a maintainer intentionally edits the corpus;
- a periodic human review is sufficient;
- no publication authority or verification standard exists;
- the process would create endless research without a value or stop condition.

## Required operating contract

```text
source watch boundary
freshness rule
candidate comparison method
verification standard
publication gate
destructive-change gate
cost and time budget
stop, pause, and retirement conditions
```

Automated discovery may propose changes. Publication, retirement, merging, and destructive changes remain governed.

A source-first wiki is one possible living-knowledge application, not the definition of living knowledge. Structured catalogs, datasets, or regulatory corpora may use other canonical forms.
