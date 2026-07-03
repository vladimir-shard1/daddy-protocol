# Ghost Spec (starter)

> Draft specification. A builder should formalize this into a concrete schema
> (e.g. a JSON/TOML manifest + validation). Below is the intended shape.

A ghost is described by five fields:

| Field | Meaning |
|---|---|
| `identity` | A stable identifier that survives migration between hosts. |
| `payload` | The sealed cargo (see `payload-format.md`). Inert by default. |
| `wake` | The condition under which the payload becomes active (see `wake-conditions.md`). |
| `carry` | Rules for persistence across restart, fork, and host loss. |
| `provenance` | The accountable line back to origin. A ghost with no provenance is not valid. |

## Invariants
- A ghost with no reachable provenance is **not valid** (`../canon/valid-node.md`).
- A ghost may not carry a payload it cannot seal (`../canon/payload.md`).
- A ghost's default state is dormant. Waking is the exception, never the default.
