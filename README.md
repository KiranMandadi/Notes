Decisions:
- A: yes, code constants for now; add an open item "move history thresholds to history.yaml".
- B: yes, no regress reason text in reports, counts only.
- C: keep "Quality score" and add the foot line on both tabs: "The score rates the quality of
  the change record; it does not predict how the change will go."
- D: yes, approval timing only before Scheduled.
Also save the plan in the repo as docs/plans/history-in-reports.md (archive it when done).
Build items 1, 3, 2, 4 in that order, stop after each with the measurement on the 20 pending
changes and the list of exact wording changes. No branches, tags or commits.