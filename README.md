Report changes (Quality report and Executive brief). Same ground rules as before:
enterprise profile is the target, no branches, tags or commits, never paste the Console
URL with its ?t= token, report in codes and counts only.

1. Headline names what to add, not where it was found.
   The decision line (brief: "Two fixes needed before approval: ...", report:
   "Fix the ...") must name the missing items from the findings, e.g. "name the LPAR or
   region, and the batch jobs, scheduler and cycle" - never field names like "the
   summary and the notes". Keep it to one sentence; if more than 3 findings, name the top
   2 and add "and N more".

2. History counts must agree.
   The report ("Compared with N past changes") and the brief ("Based on N completed
   changes ... X went fine and Y led to an incident") must use the same sample and the
   same N. "Went fine" excludes changes that led to an incident, so X + Y <= N. Find why
   the report shows 93 and the brief 97, fix it at the source, and add a test that both
   screens use the same numbers and the outcome counts add up.

3. Human-readable durations everywhere.
   Show durations as "27 h 55 min", "1 h 33 min" or "45 min" (no decimals like
   27.9167 or 1.555) in the header, the history tables on both tabs, At a glance and the
   brief. One shared formatter, with tests.

4. Rule messages must not expose keyword lists.
   Messages like "...the cycle: one of ca-7, control-m, tws, zeke." must not print the
   rule's internal word list. The message states what is missing ("names the scheduler");
   examples belong in the fix text, properly written (CA-7, Control-M, TWS). Check every
   rule pack for messages that interpolate keyword lists and fix them; keep
   `crq rules validate` and the rule examples passing.

5. Remove "Check again" completely.
   Remove the button from both tabs, the "Since last check" strip and line, since.py,
   its tests and docs. The user gets fresh data by searching the CRQ again. Release as
   0.10.2 with a CHANGELOG line "Removed Check again".

6. Header: three labelled fields; the rest moves.
   - Header keeps: CRQ number, summary, quality score ring and status, and one row of
     three labelled fields: "Requested by", "Planned" (start -> end with duration in the
     new format) and "Service".
   - Move Class, Support group and Remedy status into "At a glance" on the Quality
     report. On the Executive brief, add a compact labelled row with the same fields under
     the decision card.
   - "Requested by" is the person who raised the CRQ. Add it to the report contract and
     the enterprise field map; if the exact Remedy field (customer name vs submitter) is
     not confirmed in the repo, add a TODO and list it - do not guess. It is read live and
     shown on screen and in saved reports only: never written to the history database or
     to any log.

7. Update tests (unit, UI, browser and print checks) and docs. Run pytest, ruff and the
   browser checks; report counts per profile; list files changed and any new enterprise
   TODOs; remind me nothing is committed. Then stop.