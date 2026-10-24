Decision: identification is reliable only for mainframe. New design - measure first, then stop:
1. Apply your 4 recommendations (service pattern alone -> Low; drop tier-2 "Database"; CI class alone
   -> Medium; kubernetes -> Low). Mainframe from tier/reliable words runs the MF pack normally.
2. Remove CL-02 as a scored finding.
3. Propose a "general application" pack that runs on every change not identified as mainframe:
   the most valuable MS/PCF/INF checks rewritten to be platform-neutral (release/version named,
   deployment method stated, health checks and rollback trigger stated, hosts/CIs affected named),
   each with severity, message, fix and pass/fail examples. Specific PCF/INF/DB packs run only on a
   High signal; otherwise At a glance shows "Possible: <platform>".
4. Treat configuration as a change type (detected by action phrases such as "update config",
   "change property", "feature flag"), running the CFG rules when it applies.
5. Measure on the 16 pending and 6,376 past changes: findings per rule and status split before/after;
   and on the 29 marked rows, how many marked platforms' key checks are now covered.
Write the proposal into work/platform-id/phase0-design.md. No code or profile changes; no branches,
tags or commits.