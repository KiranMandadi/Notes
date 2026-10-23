Decisions:
- CC-06 / MF-05: keep the window-sentence rule. Add to window_words: downtime, outage,
  maintenance, nightly, overnight run, weekday names (Monday-Sunday), weekend, cutover. Bump
  quality_rules.yaml, measure again (pending/past per rule and status split), and list 10 changes
  (CRQ id + rule id only) that are still flagged by CC-06 and 10 by MF-05 for me to spot-check.
- The diffs for core.yaml, classification.yaml, change-class.yaml, mainframe.yaml,
  quality_rules.yaml and the new template_questions.yaml are approved. After the measurement,
  record the new enterprise SHA-256 baseline.
Run scripts/check.py; codes and counts only; no branches, tags or commits; then stop.