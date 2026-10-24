Decisions on docs/plans/common-validation-rules.md:
- Drop C1 and C7 (never fire; Product Name covered by Q-COMPLETE-01).
- D2 scope: rules/global/common-validation.yaml (owner Change Management office) with CV rules for
  C2, C3, C5, C6, C12. C8 and C11 go in a team-scoped file that applies only to the support groups
  in the enterprise profile's support-group list (owner: our team) - propose the exact mechanism
  (custom/ with applies_when on support group, or service files).
- C6: both values "No Testing-Manager Approved" and "Testing Not Possible"; exclude Standard changes.
- C8: Business Justification, Test Plan, Technical Design, Risk Assessment (Backout stays with
  Q-COMPLETE-02); Minor.
- C2, C3, C11: Minor. C5, C6: Major. C12: as proposed (CV-12, shadow).
- Task rules ignore tasks with status Closed, Cancelled or Bypassed.
- C4 freeze justification = Work Detail type "Restriction Approval Notes" or "Restriction Exception".
- Defer C4, C9, C10 until the fields are confirmed; mark them TODO with the exact
  crq check-fields --remedy-names steps (also confirm whether "Risk Level - Computed" differs from
  Risk Level). Priority and Pre-Implementation testing: add to the live field map only after I confirm
  the names.
- Copy the measurement scripts from the session folder into work/common-validation/ (git-ignored).
Build Phase 1: all rules status shadow; crq rules validate and the catalogue updated; re-measure and show
the status split if they were active (global only, then global + team). Results for the current
active rules must stay identical. Run python scripts/check.py --browser. No branches, tags or commits.