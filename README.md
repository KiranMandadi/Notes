Fix: At a glance shows "Platforms: Mainframe · Batch" as if confirmed, while CL-02 says the
platform is only suggested (from the word "Control-M" in the summary). Make the report consistent:
- Platforms in At a glance (Quality report), the Executive brief and Send to owner distinguish:
  confirmed (categorization or CIs) = normal chip; suggested only (text) = outlined/grey chip
  "Suggested: <platform · sub-type>" with a note naming the field it came from and a tooltip
  "Confirm by setting the categorization or linking the CIs in Remedy"; none = "Not identified".
- The report contract marks each component's strength (confirmed/suggested) if it doesn't already;
  agents' instructions say never present a suggested platform as confirmed.
- Verdict headline: if more than 2 fixes, name the top 2 and "and N more" so it isn't cut off.
- Add a contract test (suggested-only change shows "Suggested", not a confirmed chip) and a browser
  check. Run python scripts/check.py --browser; no branches, tags or commits; then stop.