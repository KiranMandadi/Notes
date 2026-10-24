Tidy work/platform-id/:
- Copy phase0-design.md to docs/archive/platform-identification-design.md (check it contains only
  codes and counts - no change text, names or summaries; redact anything else) and add it to
  docs/archive/INDEX.md. Link it from docs/quality-rules-v2.md and the open items D10, D11, K4, K5.
- Delete work/platform-id/phase1-profile.diff.
- Keep validation-set.csv, validation-key.json and score.py in work/platform-id/ (git-ignored); add a
  short README.md there explaining how to add rows and re-score, and that the folder must never be
  committed.
- Confirm work/ is still git-ignored. No other changes; no branches, tags or commits.