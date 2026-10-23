Restyle the verdict ribbon at the top of the Quality report (and the matching decision card
on the Executive brief) to be cleaner. Same ground rules: no branches, tags or commits; never
paste the Console URL with its ?t= token; enterprise profile and config.py untouched.

1. Background white like the other cards (no light-red fill), 1px border as other cards, plus a
   4px left accent bar in the status colour (Blocked red, Needs work amber, Ready green).
2. Status label as a pill using the same colours as the header status pill, e.g.
   "BLOCKED · Fix before review". Warning icon in the status colour on white (no pink square).
3. Headline in the normal ink colour, max 2 lines; summary line muted, unchanged text.
4. Blockers / Major / Minor counts use the SAME colours as the severity pills in Issues to fix
   (use the shared tokens, not new colours): number and label in the pill's text colour on the
   pill's background tint, as compact tiles. A count of 0 is neutral grey with no tint.
5. Risk and Freeze stay neutral (ink text, muted label); use colour only when they need
   attention (Freeze clash = red, Risk High = amber).
6. Thin dividers between tiles; keep it on one row at 1440 px and stack cleanly at ~760 px;
   print in colour-safe form (accent bar and tints may drop, text must stay readable).
7. Update the browser/print checks and docs/user-guide.md if they describe the ribbon. Run
   python scripts/check.py and the browser checks; list files changed; then stop.