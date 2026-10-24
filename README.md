Decisions on work/platform-id/phase0-design.md:
- D1: CI name patterns count as Medium (not High).
- D2: agree - only Summary and Details answers count until Remedy provides the implementation plan.
- D3: retire CL-01.
- D4: database words (postgres, stored procedure, oracle db, alter table, ddl, api key) -> Low,
  unless the improved text rules (step 4) lift them to >=90% agreement.
- D5: keep the service pattern at 60% share and at least 10 past changes.
- D6: phase in. First release: findings from Medium platforms are Minor; Blockers only from High
  platforms. Full weight for Medium only after validation shows >=90% precision.
- D7: leave the candidate CI name patterns out.

Do now:
1. Record these decisions in work/platform-id/phase0-design.md (section 7).
2. Copy score.py (and anything it needs, e.g. the answer key) from the session folder into
   work/platform-id/ so validation can be re-run later; update the run command in the design doc.
3. Re-measure with these decisions: platforms per confidence level and source, findings per rule,
   and the status split (history and pending), before vs after.
4. Propose better text rules for database, PCF and infrastructure: action phrases (e.g. "upgrade
   postgres", "apply ddl", "alter table", "cf push", "upgrade stemcell", "os patch", "firewall rule")
   instead of single words; ignore negated mentions ("no db change", "no code change", "no
   infrastructure change"); weight Summary above Details/Notes. Measure agreement per word/phrase
   before and after, and the effect on the status split.
5. Tell me exactly how to fill in validation-set.csv (column names, allowed platform values, how to
   mark none), then stop and wait for me to mark it.

Codes and counts only; no code or enterprise profile changes; no branches, tags or commits.