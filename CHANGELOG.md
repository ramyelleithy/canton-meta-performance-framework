# Changelog

All notable changes to the Canton Meta Performance Framework are recorded here. This file tracks the evolution of the framework itself — not day-to-day ad account activity, which belongs in `docs/historical-analysis.md`.

Per operating rule: **from v1.0 onward, any change to this framework must be justified by new data (a new audit, a new ad set result, a new Shopify pattern), not by opinion or intuition.** Every changelog entry should be traceable to evidence recorded in `docs/historical-analysis.md`.

## v1.3 — Evidence update: Historical Pattern Discovery

**Summary:** this release is an evidence update, not a rewrite. It incorporates the account-wide Historical Pattern Discovery pass (top 5 campaigns, top 5 ad sets, top 5 ads in Canton 1, compared variable by variable) into the repository. No existing framework decision, lifecycle stage, benchmark, winner, failure, or historical conclusion from v1.0–v1.2 was removed or overwritten — every addition below is either a new appended section or a new document.

**Updated:**
- `docs/historical-analysis.md` — appended "Historical Pattern Discovery v1": top recurring campaign structure (CBO, 80%), audience (broad + Advantage Audience + no gender restriction, 100%), placements (automatic, 100%), attribution (`1d_view_7d_click_1d_ev`, 100%), optimization (OFFSITE_CONVERSIONS, 100%), creative type (STATUS/Page Post, 100%), creative origin (existing Page Post, 100% confirmed / boosted-vs-dark-ad distinction Unknown), CTA (Unknown, 0/5 determinable), and hook patterns (Unknown/Experimental, contradictory on n=2). Every finding carries its confidence classification and sample size.
- `docs/framework.md` — appended a new "Historical Evidence (v1.3)" section, separating findings into Confirmed / Likely / Experimental / Unknown Rules. Flags the one direct conflict this pass surfaced: the account's top-5 campaigns are 80% CBO, while Stage 1's existing Discovery guidance defaults to ABO (sourced originally from ولاد alone). The conflict is recorded, not silently resolved — Stages 1–4 and the existing Decision Rules Summary are untouched.
- `docs/evidence-rules.md` — added Rule 8: **historical replication must always precede optimization.** A winning pattern must be reproduced successfully before it is changed, scaled, or varied. This is why `docs/experiments-roadmap.md` opens with a zero-variable replication test (EXP-003) before any isolated-variable experiment.

**Added:**
- `docs/hypotheses.md` — the open hypothesis ledger. Ten hypotheses (HYP-001 through HYP-010) covering broad vs. interest targeting, automatic vs. manual placements, existing Page Posts vs. dark ads, images vs. videos, Advantage Audience, attribution model choice, CBO vs. ABO, optimization goal, bundle-first vs. hook-first copy, and CTA choice — each with its historical confidence, current status (Confirmed / Likely / Experimental / Unknown), supporting evidence citation, and named next experiment.
- `docs/experiments-roadmap.md` — the prioritized experiment queue. EXP-003 (Historical Replication — reproduce the best historical Benetton campaign, zero variables changed) is first and gates everything after it per the new Evidence Rule 8. EXP-004 (Existing Post vs. Dark Ad), EXP-005 (Image vs. Video), EXP-006 (Broad vs. Women 25–44), EXP-007 (Automatic vs. Manual Placements), and EXP-008 (Attribution Comparison) follow in priority order, each isolating exactly one variable — a direct structural fix for the multi-variable test design flaw already documented in `docs/failures.md` FAIL-001.

**Repository audit performed:** full link validation, orphan-document check, duplicate-file check, and cross-reference coverage confirmed across all 20 documents (see audit result recorded at the time of this release).

**Not changed:** every v1.0, v1.1, and v1.2 framework decision, lifecycle stage, benchmark, winner, failure, and experiment entry remains exactly as originally documented. The CBO/ABO conflict surfaced in this release is flagged, not resolved — resolution requires EXP-003 to run first, per the new Rule 8.

---

## v1.2 — Finalization: KPI thresholds, glossary, roadmap, repository rules

**Summary:** this release completes the documentation layer of the repository. It adds no new historical evidence and does not modify any existing framework decision, benchmark, or conclusion from v1.0 or v1.1 — everything below is additive. As of this version, documentation is complete; the repository is read-only except when updated with new evidence from real experiments (see `docs/repository-rules.md` Rule 10).

**Added:**
- `docs/kpi-thresholds.md` — Canton's own performance benchmark table (CTR, CPC, CPM, LPV, VC, ATC, IC, Purchase Rate, CPA, ROAS, Frequency), each with Current Historical Benchmark, Current Experiment Benchmark, Target, Decision Rule, and Evidence Source columns. No numbers were invented — every populated cell cites `docs/historical-analysis.md`, `docs/experiments.md`, or `docs/winners.md`; every "Target" cell is left empty, since Canton has not yet run enough controlled experiments to set a forward-looking target with evidence behind it.
- `docs/glossary.md` — a one-paragraph definition for every term used across the repository (Discovery, Validation, Scaling, Prime, Winner, Failure, Evidence, Experiment, Framework, Playbook, ABO, CBO, Broad, Interest, Lookalike, Creative, LPV, VC, ATC, IC, CPA, ROAS, CTR, Frequency, and all other repository-specific terms), each cross-referenced to its source document.
- `docs/roadmap.md` — the Meta Ads operational roadmap (not a software roadmap), structured as nine phases: Repository (Completed), Historical Analysis (Completed), Landing Pages (Completed), Benetton Discovery (Pending), Creative Validation (Pending), First Stable Winner (Pending), Scaling (Pending), Second Winning Product (Pending), Prime Framework (Pending). Each phase states its Objective, Success Criteria, and Exit Criteria, and every Pending phase is explicitly tied to the experiment/winner evidence still required to complete it.
- `docs/repository-rules.md` — the operating constitution: ten rules establishing this repository as the single source of truth, prohibiting opinion-based changes, requiring evidence (historical, experimental, or winner-based) for every framework modification, mandating that every experiment/winner/failure be logged, prohibiting overwriting history (append-only), requiring every version to be recorded here in `CHANGELOG.md`, and formally declaring documentation finished as of this version — focus shifts to execution.

**Updated:**
- `README.md` — added items 11–14 to "How AI agents must use this repository" (check KPI thresholds before quoting a metric, check the glossary for term definitions, check the roadmap for the active phase, and read `docs/repository-rules.md` first as the constitution), and added all four new files to the repository map.
- Extended the existing "See also" cross-reference footers in `docs/evidence-rules.md`, `docs/framework.md`, `docs/audit-checklist.md`, and `docs/decision-tree.md` to point forward to `docs/kpi-thresholds.md`, `docs/roadmap.md`, `docs/glossary.md`, and `docs/repository-rules.md` as applicable. No existing content, conclusion, benchmark, or rule in these files was altered — only new outbound references were appended.

**Repository audit performed:** full link validation (zero broken links across all 16 documents), zero orphan documents (every document referenced by at least one other), zero duplicate files, consistent `docs/*.md` naming and Markdown formatting, and consistent bidirectional navigation confirmed. See the audit result recorded at the time of this release.

**Not changed:** every v1.0 and v1.1 framework decision, benchmark, historical conclusion, winner, failure, and experiment entry remains exactly as originally documented.

---

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
