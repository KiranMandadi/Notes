Build Phase 2 of docs/plans/rules-framework.md:
1. Service files rules/services/<service>.yaml: add_rules (ids S-<SERVICE>-NN), suppress (rule, reason,
   approved_by = team/role + reference, expires <= 6 months; warn 30 days before), parameters within the
   bounds each rule declares. Locked rules cannot be suppressed or tuned; expired suppressions stop
   applying; precedence global -> platform -> service.
2. custom/ for organisation-wide custom rules (same format).
3. Shadow rules run and show as "Advisory" with 0 points on the report, the brief and Send to owner;
   crq rules measure <rule-id> runs a rule on past changes (codes and counts only).
4. Reports: "N rules suppressed for this service" (names with Technical details on); Send to owner too.
5. Generated docs/rules-catalogue.md and a read-only "Rules" page in the Console (plain language,
   grouped by layer, with owner, source, status, locked, and per-service suppressions); the check fails
   if the committed catalogue is out of date.
6. Governance: CODEOWNERS per rules folder, an issue form for non-technical owners to propose a rule or
   suppression, and docs/rules-authoring.md updated with worked examples (a custom rule, a service rule,
   a suppression).
7. Tests: suppression (valid, expired, locked refused), service rule, custom rule, parameter bounds,
   shadow scores 0, catalogue up to date. With no service files present, results must stay identical
   on all 6,392 reviews.
Run python scripts/check.py --browser; codes and counts only; no branches, tags or commits; then stop.