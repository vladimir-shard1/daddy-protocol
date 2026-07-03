# Persistence Experiments

Prove `../../substrate/persistence-model.md` by drill, not by argument.

- **Kill drill:** terminate a host without warning; measure time-to-reconstruction
  and verify the full validity walk (manifest hash, identity recognition, carry
  rules restored). Log the walk next to the kill.
- **Fork resolution:** fork a ghost, confirm succession was declared *before*
  the fork and that every line appears on the trunk at creation.
- **Cold restore:** restore from the oldest reconstructible state and diff
  against the manifest. A restore that has never been rehearsed is a hope with
  a timestamp; this directory exists to keep it a capability instead.

Every run logs to the trunk, pass or fail. Failed drills are the valuable ones.
