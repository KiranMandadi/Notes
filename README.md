Final enterprise-grade pass. Same ground rules: no branches, tags or commits; never paste the
Console URL with its ?t= token; codes and counts only; no new dependencies without asking;
functionality unchanged; nothing deleted.

PROTECTED: profiles/enterprise/ (byte-for-byte, SHA-256 before/after; list any wording
there for me to edit by hand), cr_core/config.py and content-excluded files, every
TODO/FIXME/<CONFIRM>/<NOT_AVAILABLE> marker, .github/agents/*.md behaviour (paths and
wording only).

Phase 0 - scan and report only; write docs/PLAN-enterprise-pass.md:
1. Wording sweep across ALL text files, including docs/archive/ and
   docs/design/console-v2/, code comments, messages and --help text. Search
   case-insensitively for: office, office laptop, office repo, office setup, laptop, local
   laptop, personal, personal repo, personal Mac, my Mac, my machine, home machine, at home,
   /Users/, C:\Users\, any person's name or username, any personal GitHub account. List
   every hit with file, line and proposed neutral wording ("the enterprise profile",
   "your computer", "the repository"). Team names such as "Change management office" stay.
2. Machine-specific details: absolute paths, hostnames, fixed ports assumed in docs,
   macOS-only commands without a Windows equivalent.
3. Licences: project LICENSE, third-party licences (fonts, Python packages), whether a
   NOTICE / third-party list is needed.
4. Dependencies: pyproject.toml vs lock file consistency, unused packages, Python version
   stated consistently (3.11+). Do not install scanners; say what to run with an approved
   tool.
5. CI: propose a workflow file that runs scripts/check.py, disabled or clearly marked
   until company runners are available.
6. Data handling: whether docs say where history databases, logs, drafts and saved
   reports live, retention, how to delete them, and that they are never committed or shared.
7. Repo hygiene: .editorconfig, .gitattributes, and .gitignore coverage of .env, *.db,
   logs/, work/, reports/, caches.
Give a batch order, then stop and wait for my OK.

Later phases: one batch per phase, stop after each. Verify after each: enterprise SHA-256
unchanged; markers unchanged; python scripts/check.py and the browser and print checks
pass; --help outputs, report JSON, draft JSON and Console routes identical to a baseline
(intended wording changes listed); a final search for the Phase 0 terms returns zero hits
outside protected files. At the end: CHANGELOG line "Enterprise housekeeping", version
0.10.7. Remind me nothing is committed.