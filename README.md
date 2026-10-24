Rules framework redesign - Phase 0, design only; write docs/plans/rules-framework.md and stop.
No code, profile, branch, tag or commit changes. Codes and counts only.
Goals: rules human-readable, editable and maintainable by tech and non-tech owners, ready to be
externalized later; support custom global rules, service-local rules, and suppressions.
Propose:
1. Rule file format: plain-language fields first (id, title, why, severity, status
   draft|shadow|active|retired, owner, source link, message, fix, question), then a `check` block
   using only the existing check types; word/phrase lists instead of regex (regex only in an
   "advanced" field); examples required. A JSON Schema for the files, validated by crq rules validate.
2. Folder layout under profiles/enterprise/config/rules/: global/, platforms/, services/<service>.yaml,
   custom/; loader reads from a configurable path (CHANGELENS_RULES_DIR) so rules can move out later.
3. Service files: add_rules, suppress (rule, reason, approved_by, expires - required), parameters
   (bounded overrides). Locked rules that cannot be suppressed (propose the list). Precedence:
   global -> platform -> service; locked always wins; expired suppressions stop applying.
4. Reports: "N rules suppressed for this service" (names with Technical details on), Send to owner too.
5. Shadow status: rule runs, shows as advisory with 0 points, and is measured on history.
6. A generated rule catalogue: a "Rules" page in the Console and docs/rules-catalogue.md (plain language,
   grouped by layer, with owner, source, status, and per-service suppressions).
7. Migration plan for the existing 62 rules into the new layout with no behaviour change (prove it:
   identical findings and status split on the 16 pending and 6,376 past changes).
8. Governance: who approves rule and suppression changes (CODEOWNERS per folder), versioning, and
   how a non-technical owner proposes a change.
List decisions for me at the end.