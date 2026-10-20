Production-readiness review. ChangeLens is now an enterprise project used only with the
enterprise profile, and more people will work on it. Same ground rules: no branches,
tags or commits; never paste the Console URL with its ?t= token; codes and counts only;
no new dependencies without asking; functionality must not change.

PROTECTED (never edit): profiles/enterprise/ (byte-for-byte, SHA-256 before/after),
cr_core/config.py and any content-excluded file, every TODO/FIXME/<CONFIRM>/
<NOT_AVAILABLE> marker, open action items in docs/roadmap.md, PLAN-*.md and CHANGELOG,
docs/archive/, docs/design/console-v2/, past CHANGELOG entries' meaning.

Phase 0 - review only; write docs/REVIEW-production-readiness.md. Read every file and
list findings with file, severity (High/Medium/Low) and proposed fix, grouped as:
1. Terminology: wording like "office", "office setup", "office laptop", "personal",
   "my laptop", "sample", "demo" that should say "enterprise profile" or "setting up the
   enterprise profile" - in README, docs, agent and Copilot instruction files, --help
   text, error and UI messages, comments.
2. Personal traces: links or references to a personal GitHub account or repo, personal
   names or paths, machine-specific paths. Propose neutral wording (for CHANGELOG keep
   the entry, drop the personal link).
3. Onboarding: what a new user needs and what is missing or unclear. Propose one guide,
   docs/setup-enterprise.md: prerequisites (Python 3.11+), venv and install from the lock
   file, selecting the enterprise profile, .env from a committed .env.example (no real
   values), crq login, crq check-fields, first history load (manual), crq ui,
   troubleshooting for known errors.
4. Team workflow: CONTRIBUTING (single check command, minimal-test rule, how rule packs
   and the enterprise profile are changed and owned), a CODEOWNERS proposal, release and
   versioning notes, one script or make target that runs ruff, crq rules validate and
   pytest.
5. Code quality (no behaviour change): inconsistent error codes or messages, missing
   docstrings or type hints on public functions, dead TODOs that are actually done,
   confusing names, duplicated helpers, anything logging values it should not.
6. Security docs: whether SECURITY.md matches the real controls (local-only Console,
   session token, CSP and Host/Origin, untrusted change text, create gate and confirm
   token, dedupe, no retry, history stores no people, credentials only via keyring).
7. Items in protected files that need a human edit (list only).
Give a proposed batch order, then stop and wait for my OK.

Later phases (one batch per phase, stop after each): apply only the batches I approve.
After each batch verify: enterprise SHA-256 unchanged; ruff, crq rules validate, pytest,
browser and print checks pass (the 2 "waiting on config.py" tests listed separately);
--help outputs, report JSON, draft JSON and Console routes identical to a baseline taken
before the first batch (version and intended wording changes excepted - list each one).
Update CHANGELOG once at the end (version 0.10.5). Report files changed; remind me
nothing is committed.