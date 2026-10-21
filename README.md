Decisions:
- Q1: repoint all 18 references to docs/setup-enterprise.md, then move
  loader/OFFICE_SETUP.md into docs/archive/ (listed in INDEX.md). No "office" path left in
  the active project.
- Q2: yes, reword archived records and past CHANGELOG entries to neutral wording, keeping
  the meaning. Yes, exclude this plan from the final search and archive it at the end.
- Q3: write "as company policy requires" for retention of reports, drafts and logs, and
  add "Retention periods" to docs/open-items.md under Decisions pending. Replace "a report
  can be emailed" with: reports contain change text and a person's name and may only be
  shared through approved company channels.
- Q4: yes, add THIRD-PARTY-NOTICES.md (mark the 10 unverified platform packages as
  "Unverified - check on Windows/Linux").
- Q5: yes - list the exact LICENSE line for me to edit by hand; do not edit it.
- Q6: keep OFL.txt byte for byte; mark it -text in .gitattributes.
- Q7: leave the git history unchanged; add a note to docs/open-items.md (Decisions pending):
  "Commit author identity - confirm work identity; history rewrite only by team agreement
  before others clone".
- Q8: yes, make CI manual-only, gated by CHANGELENS_CI_ENABLED, runner labels from
  variables.

Now do batch 1 (repository hygiene) only, verify as agreed, and stop. Same ground rules:
no branches, tags or commits; profiles/enterprise/ and cr_core/config.py untouched; nothing
deleted.