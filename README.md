Summary length (Q-COMPLETE-04): set min_lengths.summary_words to 3 in quality_rules.yaml and change
Q-COMPLETE-04's severity to Minor (bump the versions of quality_rules.yaml and core.yaml). Summaries
with fewer than 3 words raise a Minor; 3 or more pass. Update the message, fix text and YAML
examples (fail: 2 words, pass: 3 words).
Measure before/after on the 20 pending and 6,376 past changes: Q-COMPLETE-04 count and the status
split. Record the new enterprise SHA-256 baseline after the change. Run python scripts/check.py
--browser; codes and counts only; no branches, tags or commits; then stop.