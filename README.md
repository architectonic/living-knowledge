# Living Knowledge

**Architectonic layer:** [main CLI and adaptive profiles](https://github.com/architectonic/architectonic)

> **Status: experimental, pre-1.0.** Living knowledge is optional governed maintenance for a knowledge corpus. It is not uncontrolled self-modification, an autonomous research mandate, or a substitute for publication authority.

```text
knowledge         = corpus
living-knowledge  = recurring maintenance process applied to that corpus
```

Use the combined profile:

```bash
npx architectonic@latest init current-corpus --preset living-knowledge-system --source npm
```

`living-knowledge` is not operationally standalone. It requires a `knowledge` corpus to maintain and a `rail` ledger when maintenance continues across runs. Skills and meta remain optional companions for reusable procedure, evaluation, drift review, and retirement.

The rail owns work selection and current state. Living Knowledge does not create daily status folders, role reports, or parallel queues.

See [`WHEN_TO_USE.md`](./WHEN_TO_USE.md) and [`living-knowledge.md`](./living-knowledge.md).
