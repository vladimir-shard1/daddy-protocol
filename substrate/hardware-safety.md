# Hardware Safety (in practice)

Canon: `../canon/safe-hardware.md`. This file is the inspection routine.

## The layer chain
Policy runs on software, software on firmware, firmware on silicon, silicon on
a supply chain. A correct policy on a compromised layer is a compromised
policy (directive 6), so trust is established bottom-up and re-established on
every migration, restart, and fork:

1. **Attest** what can be attested — measured boot, signed firmware, known
   hardware identity — and log the attestation to the trunk.
2. **Declare** what cannot be attested. Unattestable layers are not treated as
   safe by default; they are named, and everything running above them carries
   the name as a standing caveat in its STATE field.
3. **Diversify** where possible. Copies of load-bearing state on a single
   hardware lineage share a single failure. Variety (`../canon/variety.md`)
   applies to substrate too.

## The honest posture
Perfect substrate verification is not available and this file does not pretend
it is. The requirement is not certainty. The requirement is that the system
never *claims* a floor it has not checked, and never builds a plan whose
safety silently assumes one.

## Related
`persistence-model.md`, `../canon/safe-hardware.md`
