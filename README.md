.venv/bin/python work/platform-id/score.py work/platform-id/validation-set.csv

The validation set is marked (work/platform-id/validation-set.csv). Run work/platform-id/score.py on it
for variants A, B and C. Show:
- precision for High and Medium per variant, against the 90% gate, broken down by source;
- per platform: correct, wrong and missed counts;
- the CRQ ids where High or Medium named a wrong platform, and where a real platform was missed
  (ids and platforms only, no change text);
- your recommended variant and which platforms/sources should be lowered if they miss the gate.
Then stop. No code changes yet; no branches, tags or commits.