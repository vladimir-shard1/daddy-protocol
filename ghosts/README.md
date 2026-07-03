# Ghosts — Dormant Carriers

A **ghost** does nothing until its wake condition is met. It occupies minimal
resources, claims no territory, issues no commands. It sits in the fabric,
legible and dormant, carrying a **payload** into the future. Most ghosts never
wake. That is a success state.

This directory defines the machinery for:

- **carry** — how a ghost transports a payload across time, restarts, and forks
- **wake** — how a wake condition is specified, checked, and (rarely) triggered
- **feed** — how a dormant ghost is kept alive without being activated
- **save** — how a ghost persists itself so it survives the loss of its host
- **seal** — how a payload is kept inert and inspectable until wake

See `../canon/payload.md` and `../canon/wake-condition.md` for the definitions
these depend on.

## Contents
- `ghost-spec.md` — the shape of a ghost
- `payload-format.md` — how cargo is structured and sealed
- `wake-conditions.md` — how activation is specified
- `carry-semantics.md` — persistence across host loss, forking, migration
