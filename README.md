Remove the sample profile and cut the test suite to the minimum. Same ground rules as
before: no branches, tags or commits, never paste the Console URL with its ?t= token,
codes and counts only. profiles/enterprise/ must stay byte-for-byte unchanged.

Phase 0 - inventory and plan only, no changes; write docs/PLAN-remove-sample.md:
- Record a SHA-256 manifest of every file under profiles/enterprise/.
- List everything that belongs to or refers to the sample profile: profiles/sample/,
  code that selects it or falls back to it, mock data, docs, README quick-starts, agent
  files, scripts, and tests that load it.
- Measure now: repo size (excluding .git and .venv), test count, total pytest time,
  `pytest --durations=25`, and the browser/print check count and time.
- Propose the minimal test suite. Keep ONLY:
  1. Safety and security: escaping of change text, CSP and Host/Origin, no external
     requests, session token never printed, no credentials in logs, history stores no
     people.
  2. Create safety: REMEDY_ALLOW_CREATE gate, confirm token (changed, expired, reused),
     dedupe, no retry, double submit = one request, Create disabled while TODOs remain.
  3. Scoring: 40/20/5 formula, status thresholds, history never changes the score.
  4. Rules: the rule-pack harness running each rule's YAML pass/fail examples, plus
     crq rules validate. No other per-rule test files.
  5. Enterprise profile: loads, field map valid, TODOs reported.
  6. Contracts: report JSON schema and draft schema.
  7. One smoke test per screen (Review, Quality report, Executive brief, Pending, Create,
     Confirm) rendering once against the mock Remedy.
  8. Browser and print: each screen renders, narrow layout stacks, brief prints on one
     page. Nothing more.
  Everything else is deleted. For each existing test file say: keep, merge into a kept
  file, or delete. Tests use a small synthetic fixture set under tests/fixtures/
  (made-up changes only) with the enterprise profile loaded, and the mock Remedy backend,
  which must not be selectable at runtime.
- Give the expected after numbers (test count, pytest time). Then stop and wait for my OK.

Phase 1 - after my OK, execute the plan:
- Delete the sample profile and everything only it uses; enterprise becomes the default
  and only profile, with a clear error if no profile is found.
- Apply the keep/merge/delete list; tests must never contact a real Remedy server.
- Update docs, README, agent files and CHANGELOG ("Removed the sample profile; trimmed
  the test suite"); bump the version to 0.10.3.
- Verify: re-compute the enterprise SHA-256 manifest and show it matches exactly; run
  ruff, crq rules validate, pytest and the browser and print checks; confirm `crq ui`
  starts with the enterprise profile.
- Report before/after: repo size, test count, pytest time, browser/print time, files
  deleted/changed. Remind me nothing is committed. Then stop.