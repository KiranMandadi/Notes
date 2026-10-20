Decisions:
- S1: yes, add the "no tracked history database" test back (safety category).
- W1: write CODEOWNERS with clearly named placeholders (e.g. @your-org/changelens-
  maintainers, @your-org/remedy-integration) and a top comment "replace before enabling".
  Cover profiles/enterprise/, rule packs, .github/agents, the Remedy client and the create
  path.
- W5: single source of truth for the version in pyproject.toml; code reads it at runtime.
  Document the one-time "pip install -e ." in the setup guide and the CHANGELOG.
- Q1: yes, fix it so `python -m cr_core.cli` returns the same documented error codes as
  `crq` (e.g. UI_PORT_IN_USE, not INTERNAL_ERROR). Add a test.
Terminology notes: fold loader/OFFICE_SETUP.md into docs/setup-enterprise.md (leave a
one-line pointer if anything links to the old file); the Confirm message "Office fields..."
becomes "Enterprise profile fields..."; keep "Change management office" (a team name).
Security docs: list truststore in the runtime packages; reword the create retry sentence
to "a create is never retried; the dedupe reference is checked before any new attempt";
give the loader preflight report the same CSP as the Console reports.

Take the baseline, then do batch 1 (Security docs) only, verify as agreed, and stop.
Same ground rules: no branches, tags or commits; never paste the Console URL with its ?t=
token; profiles/enterprise/ and cr_core/config.py untouched.