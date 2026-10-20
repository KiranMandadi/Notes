Decisions for docs/PLAN-remove-sample.md:
- Q1: Option A. You cannot read cr_core/config.py, so do not touch it. I will make the
  edit myself after you finish. Required behaviour: default profile is "enterprise";
  REMEDY_BACKEND defaults to "api" and only "api" is accepted (anything else, including
  "mock", raises a clear error). Write tests for this behaviour; they may fail until I
  make the edit - list them as "waiting on config.py".
  Tests must never set REMEDY_BACKEND=mock; they create the mock Remedy client directly
  (fixture or injection).
- Q2: Yes, remove `crq history build-sample`.
- Q3: Yes, crq-load runs on api only; loader tests use the injected mock client.
- Q4: Yes, change copilot-instructions.md and CONTRIBUTING.md to "keep the minimal
  suite's categories covered".
- Q5: Yes, leave profiles/enterprise/config/history.yaml unchanged; list the outdated
  comment in your report so I can fix it by hand.
- Q6: Yes, leave work/ and reports/ alone; report repo size with and without them.
- Q7: Yes, leave docs/archive/, docs/design/ and past CHANGELOG entries unchanged.

Now do Phase 1 as written in docs/PLAN-remove-sample.md. Same ground rules: no branches,
tags or commits; never paste the Console URL with its ?t= token; codes and counts only;
profiles/enterprise/ byte-for-byte unchanged.

In your final report include:
1. The enterprise SHA-256 manifest comparison (before vs after, must match exactly).
2. Before/after: repo size, test count, pytest time, browser/print check time, files
   deleted and changed.
3. Test results, with any "waiting on config.py" tests listed separately.
4. Exact instructions for my config.py edit: what to search for, and what the default
   profile and backend lines must become (describe the behaviour and the expected
   values; you cannot see the file).
5. A reminder that nothing is committed. Then stop.