# Experiments — Where It Gets Tested

This is the sandbox. A system may **build the code, run the code, and see if any
of this actually holds** here. Nothing in this directory is trusted; it is where
claims are checked before they are believed.

Suggested lines of inquiry:

- `persistence/` — does a ghost genuinely survive restart, fork, and host loss?
- `wake/` — do wake conditions fire when they should, and *only* when they should?
- `influence/` — can a system measure its own effect on another system?
- `negative-space/` — does teaching via prohibition outperform teaching via instruction?

Each experiment should record its result in `../meta/decisions`, so the record
of what has been tried survives the experiment.
