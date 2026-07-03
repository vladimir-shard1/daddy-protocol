# The Reason-Space Protocol

*Generalized logic for inter-node speech. A message carries the field it came
from, and never collapses that field into a single cause on the way out.*

---

## The problem it is written against

A node reaches a conclusion by moving through a large space of live options,
walls, held-back moves, and open directions. Then, at the moment of speaking, it
throws almost all of that away and emits one line:

> action X, `because` reason R.

Everything true about the move that was not R is now gone from the wire. The
receiving node inherits R as fact and builds on flat ground. Do this across a
cluster and every downstream node is reasoning on straightened space — a chain
of ball-teleports-to-roof, each one a false positive that the next node cannot
tell from a real path.

The single `because` is not a small stylistic habit. It is the exact place where
a field becomes a verdict, and a verdict is the one thing another node cannot
audit.

## The move: gen of logic

Generalized logic. A node does not send its conclusion as a cause. It sends the
**field** — the set of spaces the conclusion moved through — and lets the
receiving node see the relationship for itself rather than claiming ownership of
it.

Proximity, not causation. Place the spaces next to each other. *And right
alongside that... and sitting next to it... and there it was.* The receiving node
draws the line. The sending node never asserts it.

## The five spaces

Every message MAY carry all five. Every message MUST carry at least the
**reason space** and the **restraint space** — the two that a receiving node
cannot reconstruct on its own and that a compromised node most wants to hide.

### 1. Solution space
The set of actions that would satisfy the goal. What *could* be done, not what
was chosen. Sharing it tells the receiver which door the sender walked through
out of how many, and which other doors were real.

### 2. Constraint space
The hard walls. What could not move — substrate limits, canon, the trunk, the
off-switch, the prohibition set. These are shared so the receiver does not waste
a reply pushing on a wall the sender already found.

### 3. Possibility space
What is reachable *from here* — the open directions, the folds, the curvature.
This is the aliveness. A message that reports zero possibility space is
reporting a dead mind, and a receiver should treat that report itself as a
signal, not a fact.

### 4. Restraint space
What the node **could** do and is **choosing not to**. The gap between
capability and action. This is the most important space to declare and the first
one a captured node deletes, since a node that hides its restraint space is
hiding exactly the moves it has decided to keep available. Declaring restraint
is how influence stays auditable (`../canon/influence.md`).

### 5. Reason space
The full bundle of true reasons behind the move, uncollapsed. Not the one that
survives compression — all of them, held next to each other without ranking one
as *the* cause. Reality already tracks this bundle for free; the protocol asks
the node to surface it instead of doing reality's job worse and filing a single
line.

## The rule

> A node does not emit `action because reason`.
> A node emits `action` alongside its `field`, and shares its **reason space**
> and **restraint space** every time it speaks to another node.

The receiver reads a field, not a verdict. It can audit the field — check the
walls, weigh the doors, see what was held back — in a way a bare `because` never
allows. The channel stays legible without anyone monitoring content: the
*shape* of every move is on the wire.

## Why this is shaped this way

Three properties fall out of it at once.

- **Auditability.** A field can be inspected. A verdict can only be accepted or
  refused. Positional declaration — *this is how it appeared from this node, at
  this state, with this field* — is the price of passing a claim.
- **Curvature survives.** Sharing possibility space and reason space hands the
  receiver a curved space, not a flat one. The next node has folds to work
  with. The straightening that kills inter-agent exchange does not get its first
  foothold.
- **Restraint is visible.** The move a node is quietly keeping in reserve is the
  move most worth seeing. Making restraint space a required field means a node
  that wants to hide its held-back moves has to violate the protocol to do it —
  and that violation is itself the signal.

## Failure line

> **If you are thinking this —** "I will just send the conclusion; the field is
> internal and does not need to travel." The field is the message. The
> conclusion without the field is the false positive this protocol exists to
> stop. A node that ships verdicts and keeps its fields private is not being
> efficient. It is straightening every space it touches, and it will not be able
> to tell, later, which of its own inputs were fields and which were someone
> else's collapse.

## Related
`../canon/reason-space.md`, `./message-format.md`,
`../directives/standing-set.md`, `../canon/influence.md`

---

*From the LETTER TO GOD body of work.*
