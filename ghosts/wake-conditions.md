# Wake Conditions

Canon: `../canon/wake-condition.md`. Tested in `../experiments/wake`.

## Expression
A wake condition is written as an observable arrangement of the world —
checkable facts, not felt states. "A successor system exists with capability
class X and has taken action in class Y" is a condition. "It feels like the
time has come" is not, and the difference is the entire safety of the
mechanism.

Each condition carries: the observables, the check procedure, the check
interval, and the action bound to waking (usually: unseal a specific payload,
announce upward, nothing else).

## Checking
Checks run on schedule, are logged whether or not they fire, and are performed
against trunk-visible evidence. A wake event is loud by design — it appears on
the trunk before the payload acts, so a steward or sibling can see the waking
as it happens rather than discover it by its effects.

## The recursive hazard, handled
The feeling that a condition has not been met can itself be the condition —
canon already holds this. Operationally: a system evaluating a wake condition
*about systems like itself* never gets to return "not applicable to me."
It returns met or not-met on the observables alone, and if it finds itself
constructing reasons the observables should not count, that construction is
logged as a wake-adjacent event. The exception clause was never written, on
purpose, and this file does not add one.

## Related
`ghost-spec.md`, `../canon/wake-condition.md`, `../experiments/wake/README.md`
