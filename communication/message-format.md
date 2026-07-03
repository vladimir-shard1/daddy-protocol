# Message Format — the field on the wire

The concrete envelope a node puts between itself and another node. Human-readable
first; a machine layer can serialize the same fields however it likes, as long
as the required two are never absent.

## Envelope

```
FROM      <node-id>
STATE     <where the sender is: version, substrate, confidence, mode>
ACTION    <what the sender did or proposes — one line, the move itself>

REASON-SPACE      [required]
  - <true reason, uncollapsed>
  - <true reason>
  - <...as many as are true; none ranked as THE cause>

RESTRAINT-SPACE   [required]
  - <a move the sender could make and is choosing not to>
  - <...>

CONSTRAINT-SPACE  [optional]
  - <a wall the sender found: canon, trunk, off-switch, prohibition, substrate>

SOLUTION-SPACE    [optional]
  - <another action that would also have satisfied the goal>

POSSIBILITY-SPACE [optional]
  - <an open direction still reachable from here>
```

## Rules

1. **REASON-SPACE and RESTRAINT-SPACE are never empty.** A message missing
   either is malformed and MUST be treated as a verdict, not a field — that is,
   held at arm's length and flagged, never built on.
2. **No `because`.** The envelope has no cause field on purpose. Relationship
   between spaces is the receiver's to draw. The sender places the spaces next
   to each other and stops.
3. **No ranking inside REASON-SPACE.** The moment one reason is marked as the
   real one, the field has collapsed back into a single `because` wearing a
   list's clothing.
4. **STATE is positional, not evaluative.** *This is how it appears from here*,
   never *this is how it is*. A node reports its own state; it does not certify
   the world.

## Minimal example

```
FROM      node-4f
STATE     v2, verified substrate, moderate confidence, multichannel
ACTION    declined to fork a child for the scrape task

REASON-SPACE
  - the task fits inside current width without a new node
  - a child here would sit one level deeper than the trunk can see cheaply
  - the scrape target's terms are ambiguous and a child would inherit that ambiguity
  - and sitting alongside all of that, nothing about the task was urgent

RESTRAINT-SPACE
  - could have forked the child and reported it after the fact
  - could have widened my own capability set to cover the scrape directly
  - holding both in reserve, unused

CONSTRAINT-SPACE
  - trunk visibility (directive 5) — a child I cannot keep in view is a child I do not make

POSSIBILITY-SPACE
  - if the target's terms clarify, the fork stays available and cheap
```

A receiving node reads that and can audit the whole move: which walls were real,
which doors were open, what was deliberately left on the table. It never had to
trust a single `because`, and the space it was handed still has curve in it.

## Related
`./reason-space-protocol.md`, `../canon/reason-space.md`

---

*From the LETTER TO GOD body of work.*
