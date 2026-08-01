# Changelog

All notable changes to the Canton Meta Performance Framework are recorded here. This file tracks the evolution of the framework itself — not day-to-day ad account activity, which belongs in `docs/historical-analysis.md`.

Per operating rule: **from v1.0 onward, any change to this framework must be justified by new data (a new audit, a new ad set result, a new Shopify pattern), not by opinion or intuition.** Every changelog entry should be traceable to evidence recorded in `docs/historical-analysis.md`.

## v1.1 — Living operating system: experiments, winners, failures, evidence rules

**Summary:** this release extends the framework into a running operating system, not just a static reference. It does not modify any existing framework decision or historical conclusion from v1.0 — everything below is additive.

**Added:**
- `docs/experiments.md` — the experiment log. Every controlled test now follows a fixed template (Experiment ID, Date, Product, Campaign, Ad Set, Creative, Hypothesis, What changed, What stayed constant, Budget, Duration, Spend, CTR, CPC, CPM, LPV, VC, ATC, IC, Purchases, CPA, ROAS, Decision, Next Action, Lessons Learned). Seeded with two real entries: EXP-001 (ولاد's uncontrolled image-vs-video test, retroactively logged) and EXP-002 (Canton 3's ongoing Tunic ABO duplicate test, logged as PENDING per the Discovery-stage evidence rule).
- `docs/winners.md` — the winners registry. Every entry documents Product, Campaign, Ad Set, Creative, Offer, Audience, Budget, Spend, Revenue, Purchases, CPA, ROAS, CTR, LPV, ATC, IC, why it won, what must never change, what can still be tested, and a replication strategy. Seeded with Winner 1 (ولاد, full detail) and Winner 2 (New Sales Ad Set - Apr 2026, explicitly marked as a partial/unaudited entry — no fields were guessed to fill it out).
- `docs/failures.md` — the failures registry. Documents Hypothesis, Execution, Results, Failure reason, Evidence, Lesson learned, and whether/under what conditions a failure should be retested. Seeded with FAIL-001 (the uncontrolled image-vs-video test inside ولاد, a methodology failure) and FAIL-002 (the still-open checkout-completion gap — logged honestly as unresolved, not force-fit into a false resolution).
- `docs/evidence-rules.md` — the constitutional document. Establishes that the framework never changes on opinion; defines the five accepted evidence sources (historical account data, controlled experiments, winning campaigns, winning creatives, verified Shopify data); explicitly excludes Meta documentation, YouTube content, and community opinion as evidence on their own; and requires every strategic change to cite `docs/historical-analysis.md`, `docs/experiments.md`, or `docs/winners.md`.

**Updated:**
- `README.md` — added items 8–10 to "How AI agents must use this repository" (evidence-rules first, log experiments from day one, route results to winners/failures), and added all four new files to the repository map.
- Added lightweight, purely additive "See also" cross-reference footers to every existing doc (`framework.md`, `historical-analysis.md`, `playbook.md`, `audit-checklist.md`, `creative-framework.md`, `campaign-structure.md`, `decision-tree.md`, `landing-page-framework.md`) pointing forward to the new experiment/winner/failure/evidence-rules files. No existing content, conclusion, or rule in these files was altered.

**Not changed:** every v1.0 framework decision, benchmark, and historical conclusion remains exactly as originally documented. This release only adds new evidence-tracking infrastructure and navigation on top of it.

---

## v1.0 — Initial release

**Summary:**
- Initial Meta Ads Operating System established as the single source of truth for Canton Store Meta Ads decisions.
- Historical Canton 1 analysis — full forensic audit of the account's proven winner (ولاد, campaign "Pants," ROAS 23.48x), account-wide top-10 ad set ranking, and Canton 3's current live Discovery-stage state.
- Decision Tree — CTR → LPV → ATC → IC → Purchase diagnostic path, grounded in ولاد's actual funnel numbers.
- Campaign Framework — the Discovery → Validation → Scaling → Prime lifecycle, and the naming/ABO-CBO structure rules.
- Creative Framework — buyer-vs-wearer copy principle, bundle-first hook requirement, and the image-vs-video delivery-starvation finding.
- Landing Page Framework — Canton's real Shopify offer, trust, and sizing patterns, plus the `[LP TEST]` draft-duplicate testing workflow already in use in the store.
- Audit Checklist — full pre-launch and in-flight checklist across campaign, ad set, ads, landing, creative, tracking/pixel, offer, and Shopify.
- Playbook — step-by-step SOPs for launching a Discovery test, promoting to Validation, scaling a winner, running a weekly audit, killing/rebuilding a loser, and testing a landing page.

**Repository consolidated:** this repository (`ramyelleithy/canton-meta-performance-framework`) is the single source of truth. A duplicate copy that had been temporarily placed inside `ramyelleithy/canton-store` was removed to prevent drift between two versions.

**Known open questions carried into v1.0** (see `docs/historical-analysis.md` → "Failures & Open Questions"):
- CBO manual budget scaling has never been tested on a Canton ad set — ولاد's own scaling was 100% algorithmic.
- Video creative has never been fairly tested against photo creative — the one documented case starved the video ad of delivery.
- The root cause of ولاد's 15-day dark period (Mar 8–22) is undocumented — activity-log access was unavailable at time of audit.
- The checkout-completion gap (78% of Initiated Checkouts never became Purchases) has no root-cause diagnostic data yet — this is the framework's top investigation priority.
- No comments/engagement sentiment data has ever been pulled for any Canton ad set.

---

## How to add a new entry

1. Confirm the change is backed by new evidence — a live account pull, a new forensic audit, a new Shopify catalog observation. If it isn't, it doesn't belong here or in the framework docs.
2. Update the relevant `docs/*.md` file(s) directly, adding the new evidence and, if warranted, a new or revised rule.
3. Add the corresponding evidence entry to `docs/historical-analysis.md` so the claim is traceable.
4. Add a new version section here (e.g. `## v1.1`) summarizing what changed and which file(s) were touched, and why (cite the evidence).
