Two small report changes. Same ground rules as before: enterprise profile is the target,
no branches, tags or commits, never paste the Console URL with its ?t= token, codes and
counts only.

1. Header (both tabs, Quality report and Executive brief), layout unchanged:
   - CRQ number becomes the title: about 26 px, monospace, semibold, white; keep the
     copy button beside it.
   - Summary becomes the subtitle: about 16 px, regular weight, colour #C9D3E4, at most
     2 lines with ellipsis, full text in the tooltip as now.
   - Spacing: 6 px between CRQ and summary, 12 px between summary and the labelled
     fields (Requested by, Planned, Service).

2. Issues to fix (Quality report only):
   - Add a column header row styled like the history table headers (small, muted,
     uppercase, one baseline): "Severity", "Points", "Issue", "How to fix", aligned to
     the existing columns.
   - Use proper table semantics (or ARIA columnheader roles) so screen readers announce
     them.
   - Below about 760 px hide the header row and keep the current stacked layout. Print
     shows the headers.

Check both at 1440 px, about 760 px and in print. Update tests and docs/ui.md. Run pytest,
ruff and the browser and print checks; report counts per profile; list files changed;
remind me nothing is committed. Then stop.