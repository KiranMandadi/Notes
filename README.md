Add common change validation rules (from the team's Confluence validation pages, common items only).
Phase 0 = design + measurement only; write docs/plans/common-validation-rules.md and stop.
No profile, code, branch, tag or commit changes. Codes and counts only.

Rules to add (global, apply to every change). Every new rule starts as status: shadow.
Proposed severity in brackets; source = the Confluence validation pages.
C1  Reason for Change is not blank. [Minor]
C2  Urgency is 1 or 2, Impact is 1 or 2, or Priority is High/Critical -> "reduce unless intended";
    one finding listing which of the three. [Minor]
C3  Computed risk level above 3 -> "confirm the risk is calculated correctly". [Minor]
C4  FreezeScope (In Scope of Restriction) is not blank; if "Yes", FreezeType is not blank AND a
    justification is present in Work Details. [Major] Relate to CC-05 (no double counting).
C5  Pre-Implementation testing is not blank. [Major]
C6  If Pre-Implementation testing indicates no testing / manager approved, a Work Detail of type
    "No Testing Attestation" is present. [Major]
C7  Product Categorization Tier 2, Tier 3 and Product Name are not blank. [Minor]
C8  Work Details contain entries of type: Backout Plan, Business Justification, Test Plan,
    Technical Design, Risk Assessment (one finding listing the missing types). [Major]
C9  Every task not Closed/Cancelled has a scheduled start and end time. [Major]
C10 The first task's start equals the change's scheduled start and the last task's end equals the
    change's scheduled end (ignore Closed/Cancelled tasks). [Minor]
C11 At least one CI is linked with an "Impacts" relationship. [Minor]
C12 Tighten the template impact-question rule: answers "N/A", "Not Applicable", "NA", "None" do not
    count as answered.
Not new rules: window > 24 h is covered by CC-06; approval cut-off by CC-01 and the approval-timing
chip - confirm and note in the plan.

Phase 0 deliverables:
1. Field availability for every field used (Reason for Change, Urgency, Impact, Priority, Risk Level
   computed, FreezeScope, FreezeType, Pre-Implementation testing, Product Cat Tier 2/3, Product Name,
   Work Detail types, task status/start/end, CI relationship type): is it in the enterprise field map
   and in the history? If not, mark TODO and list the check-fields step. Do not guess field names.
   A rule whose field is unavailable is listed as "not checked", never failed.
2. Actual values seen in history for Pre-Implementation testing, FreezeScope, FreezeType and Work
   Detail types (counts only), so the wording in C4/C6/C8 matches real values.
3. Overlap with existing rules (Q-COMPLETE-*, CC-05, CC-06, CC-01, template-question rules, GEN-*):
   keep / replace / merge, with reasons.
4. Shadow measurement on the 6,376 past and 16 pending changes: per rule how often it applies and
   fires, and the status split if each were active.
5. Rule ids, file placement in the framework, and wording (title, why, message, fix, question, examples).
Then stop for my decisions.