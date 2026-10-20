Report polish (Quality report and Executive brief). Same ground rules: enterprise profile
is the target, no branches, tags or commits, never paste the Console URL with its ?t=
token, codes and counts only.

1. Header layout:
   - Line 1: CRQ number small (about 15 px, monospace, muted teal) with a small copy
     button (copies the CRQ number only; shows "Copied").
   - Line 2: the change summary as the page title: 22 px, semibold, white, at most 2
     lines, ellipsis if longer, full summary in a tooltip (title attribute, plain text,
     escaped). The full summary stays in Description and notes.
   - Line 3: the three labelled fields as now (Requested by, Planned, Service).
   - Remove the "60 of 100" text next to the ring; keep the ring, "Quality score"
     label and the status pill. Same header on both tabs.
2. Evidence for missing items: when a finding is about something missing, show
   "Not found in <fields checked> (<N> characters checked)" instead of quoting the start of
   a field. Quote text only when the rule matched specific wording (for example a vague
   phrase). Apply to the report, the brief and Send to owner; add tests.
3. Points lost: show the points on each issue row in "Issues to fix" (e.g. "-20" next to
   the severity), add one line under the issues list "Score: 100 - 40 = 60", and remove
   the separate Points lost card. Move "At a glance" up into that space. Keep the brief
   consistent.
4. History table: align all column headers (What, This change, Usually, Note) on one
   baseline.
5. Check at 1440 px and about 760 px wide and in print. Update tests and docs/ui.md. Run
   pytest, ruff and the browser and print checks; report counts per profile; list files
   changed; remind me nothing is committed. Then stop.