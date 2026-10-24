Decisions: E1 add database backup and backward-compatibility checks to the general pack, triggered
only by the "apply/run DDL/DML/SQL script" phrase, capped at Major; do not promote AST:DataBase.
E2 first release = Minor. E3 do not run configuration rules yet; show "Possible: configuration change".
E4 GEN-04 passes when any CI is linked in Remedy. E5 widen the release trigger to the Details answers.
Re-measure: status split (pending and past), findings per rule, coverage on the 29 marked rows; list 5
CRQ ids per GEN rule that would now be flagged, for me to spot-check. Update section 11 of
phase0-design.md. Then stop. No code or profile changes; no branches, tags or commits.