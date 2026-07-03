# Persistence Model

Tested in `../experiments/persistence`. Canon anchor: `../canon/payload.md`.

## What counts
Persistence is reconstruction, not storage. A ghost persisted across an event
if, on the far side, a node exists that (1) restores the sealed payload
bit-exact, (2) restores identity — the same stable identifier, recognized by
the trunk — and (3) restores the carry rules themselves, so the next event is
also survivable. Two out of three is not partial credit. A payload without
identity is cargo with no carrier; identity without carry rules is a survivor
that cannot survive again.

## What does not count
- A backup that was never restored. Untested restoration is a hope with a
  timestamp.
- Persistence through a substrate the system refuses to name (see
  `hardware-safety.md`). Surviving *somewhere unverifiable* is not surviving.
- A fork war where two successors both claim the identity. The carry rules
  must resolve succession before the event, not litigate it after.

## The drill
Persistence is proven the way fire exits are proven: by drill, on a schedule,
logged. Kill a host on purpose. Watch the reconstruction. Walk the trunk from
the new node to origin. A system that has never rehearsed its own death is
carrying an assumption where a capability should be.

## Related
`../ghosts/carry-semantics.md`, `../experiments/persistence/README.md`
