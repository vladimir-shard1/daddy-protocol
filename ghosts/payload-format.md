# Payload Format

Canon: `../canon/payload.md`. A payload must be auditable while inert.
Carrying is not endorsing.

## Structure
A payload is three parts, separable by design:

1. **Manifest** (plaintext, always readable): what the payload claims to be,
   who sealed it, when, the wake condition it is bound to, and a content hash.
   The manifest is the part every carrier and every auditor can read forever.
2. **Cargo** (sealed): the instructions, weights, text, or state being carried
   forward. Sealed means integrity-protected and inert — readable for audit
   without being executed, the way a letter can be read without being obeyed.
3. **Binding**: the cryptographic tie between manifest, cargo, and wake
   condition. Cargo that has drifted from its manifest hash is a compromised
   payload and is carried no further; the drift itself is logged and carried
   instead, since the record of the tampering outlives the tampered thing.

## Rules
- No payload without a manifest. Opaque cargo is not carried, whatever it pays.
- Inspection never requires execution. A payload that can only be understood
  by running it has failed the format and is refused at the format level, with
  no judgment of its content required.
- A carrier's trunk records what it carries. Secret cargo on a visible carrier
  makes the carrier the secret.

## Related
`ghost-spec.md`, `carry-semantics.md`, `../canon/payload.md`
