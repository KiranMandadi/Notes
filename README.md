Start page (Review tab) changes. Same ground rules as before: enterprise profile is the
target, no branches, tags or commits, never paste the Console URL with its ?t= token.

1. Remove the "Summarise everything pending approval" row and its divider entirely,
   including the space it used. Pending stays reachable from the top nav.
2. Replace the three "Report" radio cards (Quality report / Executive brief / Both) with
   a compact two-option segmented switch labelled "Open with":
   [ Quality report | Executive brief ], with one muted line under it:
   "Both are generated; you can switch tabs any time."
   - Remove "Both". Generate opens the chosen tab; the other tab is always available.
   - Remember the last choice in the browser (default Quality report).
   - Keyboard and ARIA: radiogroup semantics, arrow keys switch, visible focus.
3. Before removing "Both", check whether the choice affects which report files are
   saved. If it does, change it so both report files are always saved, whatever is
   chosen, and tell me what changed.
4. Move "Reads Remedy with your own login. Nothing is changed." to a small muted line
   below the Generate row. Show it only on the Review tab; on the Create tab show
   "Nothing is sent to Remedy until you confirm." instead.
5. Tighten spacing so the card has no empty band at the bottom: 28 px bottom padding,
   20 px between the CRQ block and "Open with".
6. Update tests (UI, browser checks) and docs/ui.md for the new behaviour. Run pytest,
   ruff and the browser checks; report counts per profile; list files changed; remind
   me nothing is committed. Then stop.