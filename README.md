Decisions on D14:
1. Compare Risk Level, Risk Level - Computed and Risk Level - User Specified on the 16 pending changes
   (levels only, no text). Then CV-03 reads Risk Level - Computed; the rest of ChangeLens stays on Risk
   Level. Note the comparison result in the plan.
2. C4 justification = the "Change Freeze Justification" field OR a Work Detail of type "Restriction
   Approval Notes" or "Restriction Exception".
3. check-fields: query related forms (TMS:Task) for one known change's entries like the reports do,
   and if a related form still times out, skip it with a clear warning instead of failing; test both.
4. Add Priority, Pre-Implementation testing (ignore ztmp_PreImplementTesting), FreezeScope, FreezeType,
   Change Freeze Justification, Risk Level - Computed and task Scheduled Start/End Date to the enterprise
   field map; confirm with plain crq check-fields.
5. Build C4, C9 and C10 as shadow rules (tasks Closed, Cancelled or Bypassed ignored); re-measure
   CV-03, CV-05, CV-06, C4, C9, C10 on past and pending changes and show the status split if active.
New enterprise baseline; run python scripts/check.py --browser; codes and counts only; no branches,
tags or commits; then stop.