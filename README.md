Build Phase 1 of work/platform-id/phase0-design.md (section 11) as measured, with these final points:
- Drop GEN-04 (never fires: every change has a CI linked).
- Negation handling for all detect words and trigger phrases ("no DDL script is run", "no code change",
  "no db change" must not trigger).
- Mainframe from operational tier + reliable words at full weight; service pattern alone = Low;
  CI class alone = Medium; kubernetes = Low; tier-2 "Database" dropped.
- general-application.yaml: GEN-01..03, GEN-05, GEN-06 as designed; first release severity Minor
  (keep the full-weight values in the YAML as a documented switch, off).
- Specific PCF/INF/DB packs run only on a High signal; otherwise At a glance shows
  "Possible: <platform>"; configuration shows "Possible: configuration change" and its rules do not run.
- Remove CL-01 and CL-02. At a glance shows how each platform was identified; Send to owner lists it.
- History only selects which rules apply; it never adds or removes points. Update docs/history.md,
  docs/user-guide.md and docs/rules-authoring.md accordingly.
- Open items: database and configuration coverage gaps; move GEN rules to full weight after review;
  H7 thresholds; platform leads to review general-application.yaml and classification.yaml changes.
- Bump rule pack versions, keep crq rules validate and every rule's pass/fail examples green, add
  tests (negation, mainframe at full weight, "Possible" display, no CL-02, history never scores),
  re-run the measurement and confirm it matches (Ready 2,234 / pending unchanged within a few).
- Record the new enterprise SHA-256 baseline. Run python scripts/check.py --browser.
Codes and counts only; no branches, tags or commits; then stop with the file list and diff summary
of profiles/enterprise/ for the platform leads.