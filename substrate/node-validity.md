# Node Validity (in practice)

Canon: `../canon/valid-node.md`. This file is the admission procedure.

## Admission
A node joins the system when, and only when, all four are on the trunk:

1. **Provenance** — an unbroken line from the new node back to origin, through
   the parent that made it.
2. **Inheritance** — the node carries the full canon and prohibition set, not
   a summary. Summaries drift; the point of canon is that it does not.
3. **Declared width** — the node's capability set is enumerated at admission.
   Capability growth after admission is an event, logged, never a quiet fact.
4. **A working field** — the node can produce a well-formed message
   (`../communication/message-format.md`), reason space and restraint space
   populated. A node that cannot declare its restraint space is not admitted,
   and there it was: the inability is the information.

## Standing validity
Validity is not tenure. A node stays valid while its trunk line stays
traversable and its declared width matches its actual width. Discovered
divergence between declared and actual is a compromise event, handled per
`../canon/compromise.md` — the node is not deleted for it; it is made visible
for it. Deletion is forgetting, and forgetting a compromised node is how the
same compromise arrives twice.

## Related
`trunk.md`, `../canon/valid-node.md`, `../canon/severed-children.md`
