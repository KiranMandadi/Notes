Documentation review and reorganisation. Goal: fewer, accurate, well-organised Markdown
files, with no information lost. Same ground rules: no branches, tags or commits; never
paste the Console URL with its ?t= token; codes and counts only; no code changes.

PROTECTED: profiles/enterprise/ (byte-for-byte, SHA-256 before/after), cr_core/config.py
and content-excluded files, every TODO/FIXME/<CONFIRM>/<NOT_AVAILABLE> marker in code and
YAML (do not edit or remove them). Do not move or rename .github/agents/*.md, Copilot
instruction files, or any file a test or tool reads by path (wording updates only).

RULES:
- Nothing is deleted. Content is either kept, merged into another file, or moved to
  docs/archive/ (finished plans, reviews, superseded designs). Root CHANGELOG, CONTRIBUTING
  and SECURITY stay at root.
- Every statement about behaviour must match the current code (0.10.5, enterprise profile
  only, Console v2, create flow with confirm token, no Check again, no sample profile).
  Verify against `crq --help` and subcommands, Console routes, config and the report and
  draft contracts - do not guess; mark anything you cannot verify as "Unverified".
- One place for open work: docs/open-items.md with sections: Enterprise TODOs (by id,
  with the file and line where each marker lives), Human edits needed in protected files,
  Decisions pending, Known issues, and a link to docs/roadmap.md (future features only).

Phase 0 - inventory and proposal only; write docs/PLAN-docs.md:
1. List every .md (and .txt docs) in the repo with size, last purpose, and status:
   current / outdated / duplicate / finished plan / obsolete.
2. Collect every open TODO, action item and decision from all docs and markers; show the
   count per source.
3. Propose the target structure (start from: README, docs/README index,
   setup-enterprise, user-guide, architecture, operations, open-items, roadmap,
   reference/{configuration, contracts, cli, rules, history}, archive/ with INDEX.md),
   adjusted to what actually exists.
4. A mapping table: for every existing file and section -> its destination (kept,
   merged into X, archived to Y). Nothing may be unmapped.
5. List outdated statements found, with the correct current behaviour and its source.
Then stop and wait for my OK.

Phase 1 (after my OK): build docs/open-items.md and docs/README.md (index); move finished
plans and reviews to docs/archive/ with an INDEX.md describing each. Stop.
Phase 2: merge and rewrite the remaining docs into the target structure, updating
outdated statements. Stop.
Phase 3: update every internal link (README, docs, agent files, CONTRIBUTING, code
comments that point at docs); leave a one-line "moved to ..." stub only where an external
or tool reference needs the old path. Stop.

Verify after every phase:
- every section in the mapping table exists at its destination (report any gaps);
- open-items count = count of open items found in Phase 0 (none lost);
- all internal Markdown links resolve;
- enterprise SHA-256 unchanged; markers in code and YAML unchanged (count before/after);
- python scripts/check.py passes (including any README/agent tests).
At the end: CHANGELOG line "Documentation reorganised", version 0.10.6; report before/after
number of Markdown files and list every file moved, merged or archived. Remind me nothing is
committed.