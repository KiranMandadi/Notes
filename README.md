Decisions on docs/plans/rules-framework.md:
- R1: in-house validator in crq rules validate (no new dependency); still commit the JSON Schema
  file and document how to use it in VS Code for autocomplete.
- R2: defer CHANGELENS_RULES_DIR; rules stay in the profile for now. Note it as an open item.
- R3: suppressions max 6 months, renewable; check warns 30 days before expiry.
- R4: approved_by = team or role + reference (ticket id or meeting minutes date); no personal names.
- R5: locked rules must include CFG-03, Q-SAFETY-01, Q-COMPLETE-02, Q-COMPLETE-03, CC-05 and CC-02;
  show me the final list.
- R9: list the 8 switched-off rules with a recommendation each (retired or shadow); CC-07 -> shadow.
- R6-R8, R10-R13: go with your recommendations; list each decision in one line.
- Add the plan to docs/README.md.
Then build Phase 1 (format + folder layout + migration, no behaviour change) only, prove identical
results on all 6,376 past and 16 pending changes, run python scripts/check.py --browser, and stop.
Service files, suppressions, shadow and the catalogue come in Phase 2. No branches, tags or commits.