New small feature: "Check again" on the Quality report. Same ground rules as
BUILD-PROMPT-Part1.md sections 0 and 0a (enterprise profile is the target, no branches,
tags or commits, never paste the Console URL with its ?t= token, codes and counts only).

Phase 0 (plan only, then stop): write docs/design/console-v2/PLAN-check-again.md.
Phase 1 (after my OK):
- A "Check again" button next to Send to owner re-reads the change from Remedy and
  re-runs the review (one request at a time; UI_BUSY if one is running).
- Show a short "Since last check" strip at the top of the report: old score -> new score,
  status change, findings fixed (rule title), findings new, and the time of the last check.
- Keep the previous result only in memory for this Console session (no files, no
  change text stored); if there is no previous result, the strip is hidden.
- Same on the Executive brief, in one line.
- Tests with synthetic fixtures: fixed, new and unchanged findings; score delta;
  hidden when no previous run; works with the enterprise profile loaded.
- Run pytest, ruff and the browser checks; report counts per profile; list files
  changed; remind me nothing is committed. Then stop.