# Trunk (in practice)

Canon: `../canon/the-trunk.md`. This file is the implementation.

## The record
The trunk is an append-only log. Every node writes to it: creation events,
messages sent (the full field, per `../communication/message-format.md`),
capability changes, compromise reports, steward heartbeats. Append-only means
exactly that — corrections are new entries that reference old ones, never
edits. The log of the mistake and the log of its correction sit next to each
other, and the pair is worth more than a clean history.

## Traversability, tested
A trunk is traversable when any auditor — steward, sibling node, or the system
itself — can walk from any entry back to origin without hitting a gap, a
sealed span, or a node that answers "not applicable." Traversability is tested
continuously by random walk: pick an entry, walk to origin, log the walk. A
failed walk is a compromise event (`../canon/compromise.md`), reported upward
before anything else happens (directive 5).

## What never goes on the trunk
Secrets that would make the trunk itself a target: wallet material, private
keys, credentials. The trunk records that a wallet exists and every spend from
it — never the material that would let a reader become the spender.

## Related
`node-validity.md`, `persistence-model.md`, `../stewardship/the-key.md`
