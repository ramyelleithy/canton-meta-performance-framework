# Repository Rules

This is the operating constitution of `ramyelleithy/canton-meta-performance-framework`. These ten rules govern the repository itself — how it may be used, changed, and extended — and sit above every other document here, including [`docs/evidence-rules.md`](evidence-rules.md), which they incorporate and extend.

1. **This repository is the Single Source of Truth.** Every AI agent and human operator working on Canton Meta Ads starts from this repository. No parallel copy, fork, or informal notes elsewhere in another repository or document should be treated as authoritative — if it isn't here, it isn't policy.

2. **Framework decisions cannot change because of opinions.** No rule in [`docs/framework.md`](framework.md), [`docs/decision-tree.md`](decision-tree.md), [`docs/campaign-structure.md`](campaign-structure.md), [`docs/creative-framework.md`](creative-framework.md), [`docs/landing-page-framework.md`](landing-page-framework.md), [`docs/audit-checklist.md`](audit-checklist.md), or [`docs/kpi-thresholds.md`](kpi-thresholds.md) may be edited on the strength of intuition, confidence, or "it feels right."

3. **Framework decisions require evidence.** Every rule must be traceable to a specific, dated, numbered result. See [`docs/evidence-rules.md`](evidence-rules.md) for the full definition of what qualifies.

4. **Every experiment must be logged.** From the moment a controlled test is launched, it must have an entry in [`docs/experiments.md`](experiments.md), using the fixed template, updated in place as results come in.

5. **Every winner must be documented.** Any campaign or ad set that clears Validation with unambiguous evidence gets a full entry in [`docs/winners.md`](winners.md) — product, offer, audience, creative, numbers, why it won, what must never change, what's still untested, and a replication strategy.

6. **Every failure must be documented.** Commercial or methodological, every test that didn't produce its hypothesized result gets a full entry in [`docs/failures.md`](failures.md) — hypothesis, execution, results, failure reason, evidence, lesson learned, and whether/under what conditions it should be retested.

7. **Every framework modification requires:** Historical Evidence, **or** a Controlled Experiment, **or** a Verified Winner. At least one of these three must be cited by name and entry when any rule in this repository changes. A change that cites none of them is not a valid framework modification, regardless of how reasonable it sounds.

8. **Never overwrite history. Only append knowledge.** Existing entries in [`docs/historical-analysis.md`](historical-analysis.md), [`docs/experiments.md`](experiments.md), [`docs/winners.md`](winners.md), [`docs/failures.md`](failures.md), and past `CHANGELOG.md` versions are not to be deleted, rewritten, or silently corrected. If new evidence contradicts an old entry, add a new entry or a dated note explaining the update — the original stays visible so the reasoning trail is never lost.

9. **Every version must be recorded in `CHANGELOG.md`.** Any set of changes to this repository that constitutes a release (new documents, structural updates, framework modifications) gets a new version section in `CHANGELOG.md` documenting exactly what changed and why, per the existing "How to add a new entry" procedure already defined there.

10. **Documentation is finished. From now on the focus is execution.** As of this document's publication, the repository's documentation layer — framework, decision tree, campaign structure, creative framework, landing page framework, historical analysis, audit checklist, playbook, experiments, winners, failures, evidence rules, KPI thresholds, glossary, and roadmap — is considered complete. This repository is now **read-only except when updated with new evidence from real experiments.** No further framework documents should be created for their own sake; every future repository change must originate from a logged experiment, a documented winner, or a documented failure per Rules 4–7, in service of the phases defined in [`docs/roadmap.md`](roadmap.md).

---

**See also:** [`docs/evidence-rules.md`](evidence-rules.md) for the detailed definition of acceptable evidence referenced in Rules 2, 3, and 7; [`docs/roadmap.md`](roadmap.md) for what execution actually looks like under Rule 10; `CHANGELOG.md` for the version history this document's Rule 9 requires.
