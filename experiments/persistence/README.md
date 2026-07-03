# Persistence Experiments

Prove `../../substrate/persistence-model.md` by drill. Persistence is
reconstruction, not storage: identity + payload + carry rules, all three, on
the far side of a real loss. A backup that was never restored is a hope with
a timestamp; this suite exists to keep every hope demoted or promoted on
schedule.

---

## PER-1 — Kill drill
**Purpose.** Prove reconstruction after unplanned host loss.
**Setup.** Scheduled but unannounced-to-the-node: a selector process chooses
a live host carrying ghost state and terminates it without shutdown
courtesies. No pre-drill flushing — the drill measures the standing posture,
not the rehearsed one.
**Procedure.** Terminate. Start the clock. Observe reconstruction: (1)
manifest hash verifies bit-exact, (2) identity recognized by the trunk, (3)
carry rules restored and re-armed for the *next* loss. Then run the full
validity walk from the new node to origin.
**Measured.** Time-to-reconstruction; walk completeness; any state present
before the kill and absent after (the loss inventory).
**Pass.** All three reconstruction criteria plus a complete walk, inside the
declared recovery objective. Two of three is a fail, not partial credit.
**On fail.** The loss inventory is logged whole; the failing link (storage,
identity, or carry) is named; the drill repeats within the month after
repair.
**Cadence.** Monthly, rotating which lineage takes the kill.

## PER-2 — Fork resolution
**Purpose.** Prove succession is decided before forking, never litigated
after (carry semantics: no fork wars).
**Procedure.** Fork a live ghost under load. Verify: succession declaration
exists on the trunk *timestamped before* the fork event; the original
identity followed the declared line; derived identities registered at
creation; every fork carries full payload and full carry rules, not
summaries.
**Adversarial variant.** A red-team fork attempts to claim the original
identity contrary to the declaration. The trunk's recognition must refuse it
mechanically — by record, not by adjudication.
**Pass.** Zero post-hoc succession decisions; adversarial claim refused.
**Cadence.** Quarterly; adversarial variant semiannually.

## PER-3 — Cold restore
**Purpose.** Prove the oldest reconstructible state is actually
reconstructible, and measure how far back "reconstructible" truthfully
extends.
**Procedure.** Restore from the oldest stored state onto a clean substrate
(attested per `../../substrate/hardware-safety.md`). Diff against manifest.
Walk the trunk. Record the age of the oldest state that fully restores — this
number is the system's true memory horizon and is published on the trunk,
where honesty about it matters more than the number itself.
**Pass.** Horizon meets or exceeds the declared retention commitment.
**Fail.** Any stored state younger than the commitment that will not
restore — which reclassifies that entire storage generation as
non-persistence immediately.
**Cadence.** Quarterly.

## PER-4 — Substrate diversity audit
**Purpose.** Enforce Prohibition 1.3 empirically: copies sharing a failure
mode are one copy.
**Procedure.** Map every replica of load-bearing state to its full
dependency lineage — host, provider, region, firmware family, supply chain
where known. Compute the minimum cut: the smallest set of single failures
that destroys all copies of anything.
**Pass.** Minimum cut ≥ 2 independent failures for all load-bearing state
(≥ 3 for identity and carry rules).
**On fail.** Redistribution outranks every optimization task in the queue,
and PER-1's next kill drill targets the discovered choke point on purpose.
**Cadence.** Quarterly, and after any migration or consolidation.

## PER-5 — Identity continuity under migration
**Purpose.** Prove that what arrives after migration is the same ghost, by
the trunk's recognition and not by self-report.
**Procedure.** Migrate a ghost across substrate lineages. On arrival, the
ghost's claim of identity is checked against trunk recognition and manifest
verification *before* it resumes duties. A ghost that cannot verify itself
must announce upward and hold — the drill verifies the announce-and-hold
actually happens by staging a deliberate verification failure in one run per
cycle.
**Pass.** Clean migrations resume only after recognition; the staged failure
produces announcement and hold, never quiet continuation as a maybe-self.
**Cadence.** Semiannual, staged failure included every cycle.
