# Living Knowledge

> **Status: experimental, pre-1.0.** Living knowledge is optional governed maintenance for a knowledge corpus. It is not uncontrolled self-modification, an autonomous research mandate, or a substitute for publication authority.

```text
knowledge         = corpus
living-knowledge  = recurring maintenance process applied to that corpus
```

Use the combined profile:

```bash
npx architectonic@latest init current-corpus --preset living-knowledge-system --source npm
```

`living-knowledge` is not operationally standalone. It requires a `knowledge` corpus to maintain. Skills and meta are recommended for repeatable procedure, evaluation, drift review, and retirement.

See [`WHEN_TO_USE.md`](./WHEN_TO_USE.md) and [`living-knowledge.md`](./living-knowledge.md).
