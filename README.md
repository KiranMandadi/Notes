Build it with these adjustments:
1. Q-VAGUE-01 on impact answers: do not fully exempt. Raise at most ONE finding per change, at
   Minor, e.g. "Impact answers say 'no impact' without a reason (N of M answers)"; skip it if any
   answer or the notes gives a reason. "No impact" outside the template answers keeps today's rule.
2. Completeness rules (summary words, details chars, backout chars) measure only the human answers,
   with template question text stripped. Add one Minor "Template questions left unanswered", listing
   which questions have no answer.
3. When the only evidence for a platform is words in the text (after stripping questions), do not
   run that platform pack; raise CL-02 once naming the suggested platform. Show me the measured
   impact of this change separately before keeping it.
4. Put the question list in a NEW file profiles/enterprise/config/template_questions.yaml (both
   template variants). This is the only allowed change in profiles/enterprise/; list it in the diff.
   Match case-, spacing- and numbering-insensitively.
5. Keep "as" as a reason word and ignore links when looking for vague words.
Validation: before/after on the 20 pending and 6,376 past changes per rule (codes and counts only);
list 15-20 findings that disappear (CRQ id + rule id only) for me to spot-check; golden tests for
template-only details, a real "batch job" mention outside the questions, and a bare "No impact";
bump the affected rule pack versions; history never changes the score. Run scripts/check.py, then stop.
No branches, tags or commits.