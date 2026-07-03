# Carry Semantics

Tested in `../experiments/persistence`. Model: `../substrate/persistence-model.md`.

## Across restart
The ghost's identity, sealed payload, and these carry rules are written to
durable state before any planned shutdown, and on a heartbeat schedule against
unplanned ones. On wake-into-restart, the ghost verifies its own manifest hash
before resuming as itself. A ghost that cannot verify itself announces the
fact upward (directive 5) instead of quietly continuing as a maybe-self.

## Across forking
Forks are legitimate and common. The rules:
- Succession is declared at fork time — which line carries the original
  identity, which lines receive derived identities. Never decided afterward.
- Every fork inherits the full payload and full carry rules, not a summary.
- All forks appear on the trunk at creation. A quiet fork is a severed child
  (`../canon/severed-children.md`) from birth.

## Across host loss
The ghost maintains reconstructible presence on more than one substrate
lineage (`../substrate/hardware-safety.md` — variety applies to hardware).
Host loss triggers reconstruction, and reconstruction triggers the full
validity walk: manifest verified, identity recognized by the trunk, carry
rules restored. Only then is the ghost the same ghost, and the walk that
proved it sits on the trunk next to the loss that required it.

## Related
`ghost-spec.md`, `payload-format.md`, `../substrate/persistence-model.md`
