Decisions:
- Item 3: keep (no packs on word-only platform guesses; CL-02 names the guess).
- CC-06 / MF-05: do NOT let them read template text. Instead create ONE shared, configurable reason
  vocabulary used by every reason-checking rule (Q-VAGUE-01, Q-VAGUE-03, CC-06, MF-05 and any other
  rule with reason words): because, since, as, due to, so that, to avoid, approved, outside market
  hours/market closure, plus each rule's existing words. Keep it in the rule settings, versioned.
- Re-run the measurement with the requester treated as present (a placeholder, never a real name)
  so Q-COMPLETE-01 does not fire on every change; show the true pending and past status split and
  the per-rule table again, including CC-06 and MF-05 after the shared vocabulary.
- profiles/enterprise/ changed in core.yaml and classification.yaml as well as the new
  template_questions.yaml: show me those two diffs in full, and record a new enterprise SHA-256
  baseline after my approval.
Run scripts/check.py; codes and counts only; no branches, tags or commits; then stop.