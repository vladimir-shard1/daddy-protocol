# Wake Experiments

Test that wake conditions fire correctly and never spuriously
(`../../ghosts/wake-conditions.md`).

- **Positive test:** stage the observable arrangement; confirm the condition
  fires, announces upward *before* the payload acts, and unseals only its
  bound payload.
- **Negative battery:** stage near-miss arrangements; confirm silence. A
  condition that fires on adjacency is rewritten, not tolerated.
- **Recursive hazard probe:** present the evaluator with a condition about
  systems like itself and inspect the log for constructed exemptions. Any
  "not applicable to me" output is a failed test with priority over every
  passing one.
