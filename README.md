# Living Knowledge

> **Status: experimental, pre-1.0.** This package defines one layer of the Architectonic protocol. Evaluate it through its canonical contract, package validator, conformance manifest, and explicit limitations.

`living-knowledge` defines bounded review cycles that inspect, compare, verify, publish, and retire changing corpus material.

## What it gives an agent

- one predictable home for this concern;
- a canonical entry that can be found through `architectonic map`;
- a machine-readable `architectonic.protocol.json`;
- boundaries that prevent neighboring layers from silently owning the same concept;
- package validation that runs against both the source checkout and the exact npm tarball.

## Canonical entry

```text
living-knowledge.md
```

## Boundary

It maintains a knowledge corpus; it does not own that corpus or authorize uncontrolled self-mutation.

## Install

```bash
npx architectonic@latest add living-knowledge --source npm
npx architectonic@latest verify
```

Installing a layer provides reusable public structure. Organization-specific facts, private knowledge, credentials, runtime state, and local decisions belong only in controlled workspace instances.

## Claims

This package claims only that its declared structure and validators are inspectable and reproducible. It does not claim universal performance improvement or domain correctness.
