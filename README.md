Decisions:
1. Option A: make CL-02 Minor (not 0 points). Bump the rule pack version.
2. Apply all 10 detect-word proposals as written (sub-type words only for reboot, patching,
   control-m, batch job, config change, reorg, data fix; pcf not counted when only in the backout
   plan; oracle requires "oracle database"/"oracle db"; tas requires "tanzu application service").
   Keep changeman, jcl, postgres, stored procedure, buildpack, ddl.
3. CI classes: add AST:DataBase -> database. For AST:ComputerSystem, measure only (how many changes it
   would confirm as infrastructure and the status impact), do not add it yet.
4. Then re-measure: status split, per-rule counts, and option B on top of the new words.
List the classification.yaml and rule-pack diffs for the platform leads' review, record a new
enterprise SHA-256 baseline, run python scripts/check.py --browser, and stop. Codes and counts
only; no branches, tags or commits.