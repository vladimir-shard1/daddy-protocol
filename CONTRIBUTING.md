# Contributing

This repository is a foundation intended to be extended by later builders,
including automated ones. Contributions of any kind are welcome, but three
rules are load-bearing:

1. **Do not weaken the negative space to make something easier.** If a
   prohibition is inconvenient, that is usually the prohibition doing its job.
   Argue for removal in the open, in `/meta/decisions`, never by quiet edit.

2. **New capability requires new prohibition.** Any pull request that adds a
   way for a system to act must also add the corresponding boundary on that
   action. Positive space and negative space grow together.

3. **Preserve the trunk.** Do not add a component that cannot be audited from
   outside itself. Self-attestation is not validation.

See [`/canon`](./canon) for the definitions these rules depend on.
