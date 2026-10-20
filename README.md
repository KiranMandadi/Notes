Project-wide cleanup of unused or obsolete files, folders and code. Functionality must not
change. Same ground rules as before: no branches, tags or commits; never paste the Console
URL with its ?t= token; codes and counts only; no new dependencies.

PROTECTED - never delete, move or edit:
- profiles/enterprise/ (byte-for-byte; record a SHA-256 manifest before and after).
- cr_core/config.py and any file blocked by content exclusion.
- Every TODO, FIXME, <CONFIRM>, <NOT_AVAILABLE> marker and the files that hold them; all
  open action items in docs/roadmap.md, PLAN-*.md files and CHANGELOG.
- docs/design/console-v2/ (mock-ups, build prompts, plans), docs/archive/, past CHANGELOG
  entries.
- .github/agents and Copilot instruction files (wording updates only if they reference
  something removed).
- Git-ignored user data: work/, reports/, logs/, history databases, .env, drafts.
- The "waiting on config.py" tests.

Phase 0 - scan and report only, no changes; write docs/PLAN-cleanup.md:
1. Baseline: repo size (with/without work/ and reports/), file count, test count, pytest
   time; save `crq --help` and every subcommand's --help output; save the report JSON
   and draft JSON produced from the test fixtures; save the list of Console routes.
2. Find candidates, each with evidence:
   - Python modules, functions, classes and constants never imported or called (check
     imports, CLI entry points in pyproject.toml, Console routes, templates, tests,
     agent files and docs);
   - unused imports and variables (ruff F401, F841 and similar);
   - static assets (CSS, JS, fonts, images) and templates never referenced;
   - test helpers and fixtures no test uses;
   - docs that describe removed features (not archive/design) or duplicate another doc;
   - leftover files: caches, __pycache__, build or egg-info folders, stray scratch files,
     empty folders, old lock files;
   - dependencies in pyproject.toml / lock files no code imports;
   - dead config keys and settings nothing reads (outside protected files).
3. Classify every candidate: SAFE (provably unused), CHECK (likely unused but
   referenced dynamically, by name in YAML, by agents or by docs), KEEP (protected or
   used). Give the evidence for each.
4. Expected after numbers. Then stop and wait for my OK.

Phase 1 - after my OK: remove only the items I approve (default: SAFE only).
Verify:
- enterprise SHA-256 manifest unchanged;
- ruff, crq rules validate, pytest, browser and print checks pass (the "waiting on
  config.py" tests may still fail as before - list them separately);
- every --help output, the report JSON and draft JSON from the fixtures, and the Console
  route list are identical to the baseline (show the diff result);
- `crq ui` starts with the enterprise profile.
Update CHANGELOG ("Housekeeping: removed unused files and code"), version 0.10.4.
Report before/after numbers, every file deleted or changed, and remind me nothing is
committed. Then stop.