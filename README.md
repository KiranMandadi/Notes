Platform identification - fully automatic, no new Remedy fields, no maintained maps, no new steps for
owners. Phase 0 = design + measurement only, then stop. Codes and counts only; no branches, tags or
commits; do not change code or the enterprise profile yet.

Design to measure:
1. Signals, each with a strength: CI class (map the AST: names Remedy actually writes, e.g.
   AST:DataBase); CI name patterns (propose patterns from the data); operational tiers (existing);
   service pattern learned automatically by the history loader (share of the service's past changes
   per platform; refreshed by the existing manual load; no human upkeep); specific detect words only in
   Summary, Details and Implementation plan owner answers (not Notes boilerplate, Backout, Test plan;
   generic words like patching/reboot never count alone).
2. Confidence per platform: High (CI class or operational tier, or service pattern agrees with text)
   -> packs run normally; Medium (service pattern alone, or specific words in the right fields) -> packs
   run, findings capped at Major, labelled "platform identified automatically"; Low (single word in
   notes/backout only) -> no packs, At a glance shows "Possible: <platform>".
3. Remove CL-02 as a scored finding. At a glance always says how each platform was identified.
   Send to owner lists the identified platforms.
4. History only selects which rules apply; it never adds or removes points directly. Document this
   in docs/history.md and the user guide.
Measure on the 20 pending and 6,376 past changes: platforms per confidence level and source, pack
findings per rule, status split before/after.
Validation: build a set of ~40 changes across services (CRQ ids only) in a CSV for me to mark the true
platforms; report precision per confidence level once marked. High and Medium must reach >=90% before
packs run with weight. Then stop for my decision.