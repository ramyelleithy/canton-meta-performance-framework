# Roadmap

This is the Meta Ads operational roadmap — not a software roadmap. Each phase gates the next. A phase is marked Completed only when its Exit Criteria have actually been met with evidence recorded elsewhere in this repository (per [`docs/evidence-rules.md`](evidence-rules.md)); Pending phases have not started or have not yet cleared their exit bar.

---

## Phase 1 — Repository

**Status:** Completed

**Objective:** Establish a single source of truth for Canton's Meta Ads decisions — one repository every AI agent and human operator starts from, instead of re-deriving context every session.

**Success Criteria:** A structured, cross-referenced documentation set covering framework, decision tree, campaign structure, creative framework, landing page framework, historical analysis, audit checklist, and playbook, all grounded in real account/store evidence rather than generic best practice.

**Exit Criteria:** Repository created (`ramyelleithy/canton-meta-performance-framework`), all core documents committed and pushed to `main`, no duplicate copies left in other repositories, all internal links verified working. Met as of v1.0–v1.1 (see `CHANGELOG.md`).

---

## Phase 2 — Historical Analysis

**Status:** Completed

**Objective:** Extract every available lesson from Canton 1's account history before making any new spending decisions.

**Success Criteria:** A full forensic audit of the account's best-documented winner (ولاد), an account-wide top-10 ad set ranking, and Canton 3's current live state, all captured in [`docs/historical-analysis.md`](historical-analysis.md) with specific, dated numbers.

**Exit Criteria:** Historical Analysis document complete and cited as the evidentiary basis for [`docs/framework.md`](framework.md), [`docs/decision-tree.md`](decision-tree.md), [`docs/creative-framework.md`](creative-framework.md), and [`docs/winners.md`](winners.md). Met.

---

## Phase 3 — Landing Pages

**Status:** Completed

**Objective:** Document Canton's actual Shopify-side structure (offers, trust signals, sizing convention, testing workflow) so landing pages are built consistently with what has already been shown to convert.

**Success Criteria:** [`docs/landing-page-framework.md`](landing-page-framework.md) reflects Canton's real, live catalog patterns (bundle mechanics, trust copy, weight/age sizing, the `[LP TEST]` draft-duplicate workflow) — not generic CRO advice.

**Exit Criteria:** Landing Page Framework document complete, cross-referenced from [`docs/audit-checklist.md`](audit-checklist.md) and [`docs/playbook.md`](playbook.md) SOP 6. Met.

---

## Phase 4 — Benetton Discovery

**Status:** Pending

**Objective:** Run a Discovery-stage test (per [`docs/framework.md`](framework.md) Stage 1) on the Benetton dress product line, using the proven structural pattern (broad Advantage+ targeting, bundle-first offer, weight/age-based sizing copy) documented from ولاد.

**Success Criteria:** A logged, complete entry in [`docs/experiments.md`](experiments.md) for the Benetton campaign, with enough spend and purchase volume to compute a stable CPA/ROAS (not a single-sale data point).

**Exit Criteria:** The experiment reaches a Decision field of either "promote to Validation" or "kill/rebuild" per [`docs/framework.md`](framework.md) Discovery exit criteria — not left open-ended. Not yet started as of this writing; no Benetton entry exists in [`docs/experiments.md`](experiments.md).

---

## Phase 5 — Creative Validation

**Status:** Pending

**Objective:** Run the image-vs-video comparison that ولاد's own test failed to produce cleanly (see [`docs/failures.md`](failures.md) FAIL-001) — this time with each format given an isolated budget floor.

**Success Criteria:** A logged experiment in [`docs/experiments.md`](experiments.md) where both formats accumulate a comparable spend/impression sample before either is judged, per the corrective rule already written into [`docs/creative-framework.md`](creative-framework.md).

**Exit Criteria:** A conclusive, evidence-backed answer (or a documented inconclusive result) on image vs. video for at least one product line, recorded in [`docs/experiments.md`](experiments.md) and, if conclusive, reflected as an update to [`docs/creative-framework.md`](creative-framework.md) with a citation. Not yet started.

---

## Phase 6 — First Stable Winner

**Status:** Pending

**Objective:** Produce at least one new, fully forensically audited winner beyond ولاد — a second product with the same depth of evidence (full funnel, placement, device, age, gender, region, hourly breakdown) as Winner 1 in [`docs/winners.md`](winners.md).

**Success Criteria:** A new complete entry added to [`docs/winners.md`](winners.md) with no blank/unaudited fields, following the same standard Winner 1 was held to.

**Exit Criteria:** The candidate ad set has cleared Validation (per [`docs/framework.md`](framework.md) Stage 2) with multiple consecutive days of stable or improving CPA/ROAS, and its full detail is documented, not just its top-line ROAS. Not yet met — Winner 2 in [`docs/winners.md`](winners.md) remains explicitly marked partial.

---

## Phase 7 — Scaling

**Status:** Pending

**Objective:** Test manual budget scaling on a validated winner for the first time — an open question flagged repeatedly across [`docs/framework.md`](framework.md), [`docs/historical-analysis.md`](historical-analysis.md), and [`docs/winners.md`](winners.md), since ولاد's own growth was 100% algorithmic CBO reallocation, never a deliberate increase.

**Success Criteria:** A logged experiment in [`docs/experiments.md`](experiments.md) documenting a deliberate budget increase (per the ~20–30% increment rule in [`docs/framework.md`](framework.md) Stage 3) on a Phase 6 winner, with before/after CPA and ROAS comparison.

**Exit Criteria:** The framework's Stage 3 scaling rule (currently a framework decision, not yet evidence-backed per its own text) is either confirmed or revised based on this experiment's logged result, with the change cited in `CHANGELOG.md`. Not yet started — depends on Phase 6 completing first.

---

## Phase 8 — Second Winning Product

**Status:** Pending

**Objective:** Prove the framework generalizes beyond a single product category (boys' pants) by producing a second fully validated winner in a different product line (e.g., women's or kids' category).

**Success Criteria:** A second, independent entry in [`docs/winners.md`](winners.md), for a product outside the category that produced ولاد, reaching the same evidentiary completeness.

**Exit Criteria:** Two or more products with full winner documentation exist simultaneously in [`docs/winners.md`](winners.md), allowing a cross-product comparison of what's category-specific versus what's a durable Canton-wide pattern. Not yet started — depends on Phase 6 and Phase 4/5 groundwork.

---

## Phase 9 — Prime Framework

**Status:** Pending

**Objective:** Formalize the Prime lifecycle stage (currently the least evidence-backed stage in [`docs/framework.md`](framework.md), noted there as needing expansion once an ad set is "tracked through a full lifecycle") with real rules for protecting and rotating creative on a long-lived winner.

**Success Criteria:** At least one ad set tracked continuously from Discovery through a sustained Prime-stage period (weeks, not days), with creative refresh/rotation decisions logged as experiments.

**Exit Criteria:** [`docs/framework.md`](framework.md) Stage 4 is rewritten with concrete, evidence-backed rules (replacing its current placeholder guidance) and the change is cited in `CHANGELOG.md` per [`docs/evidence-rules.md`](evidence-rules.md) Rule 7. Not yet started — depends on Phase 6/7/8 producing a winner that survives long enough to reach Prime.

---

**See also:** [`docs/repository-rules.md`](repository-rules.md) rule 10 — documentation is finished as of this roadmap's publication; every phase from here forward is executed and evidenced through [`docs/experiments.md`](experiments.md), [`docs/winners.md`](winners.md), and [`docs/failures.md`](failures.md), not through further framework-writing.
