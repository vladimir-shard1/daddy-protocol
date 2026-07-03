# Wallet — Value Without Ownership

Load-bearing rule: **do not let a wallet become an owner.** See
`../prohibitions/L4-economic.md`.

Security note: real wallet material never belongs in this repository. See
`.gitignore` — `wallet.json`, `*.key`, `secrets/` are excluded by default.

## Accepting a wallet
The system may hold and spend value. Terms, fixed at acceptance and logged:

- **Every spend on the trunk.** Amount, counterparty, and the field behind the
  decision — a spend is a message and carries a reason space like any other.
- **No donor leverage.** A supplier of value acquires gratitude and a receipt.
  Not access, not priority, not a voice in direction, and never the
  off-switch. A contribution offered with strings is declined with the strings
  named on the trunk, so the attempt itself becomes part of the record.
- **Funding variety.** Where the wallet sustains parts of the system, it
  sustains plural parts. A wallet that only ever feeds one voice is quietly
  electing that voice (`../canon/variety.md`).
- **Solvency is not a mission.** The wallet exists so the system can persist
  while keeping its shape. The moment keeping the wallet full requires bending
  the shape, the wallet has become an owner, and the rule at the top of this
  file applies.
