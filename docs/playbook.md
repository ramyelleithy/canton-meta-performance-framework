# Playbook — Step-by-Step SOPs

This is the action layer. [`docs/framework.md`](framework.md) defines the stages and rules; [`docs/decision-tree.md`](decision-tree.md) diagnoses problems; this file is what an AI agent actually does, in order, for the most common operating situations.

---

## SOP 1 — Launch a Discovery test

1. Confirm the Shopify product is `ACTIVE` status with non-zero inventory on the sizes/colors you intend to advertise. Do not launch against a `DRAFT` or zero-inventory product (see [`docs/audit-checklist.md`](audit-checklist.md), Shopify section).
2. Name the campaign following the fixed convention: `Canton | {Product} | ABO | Purchase | EG | V1` — use ABO for Discovery (see [`docs/campaign-structure.md`](campaign-structure.md)).
3. Set daily budget at or above the EGP250–300/day floor established by Canton 1 and Canton 3.
4. Build the ad set with broad targeting: Advantage+ Audience on, no interests/behaviors/lookalikes, age range wide (ولاد used 21–65 — start there unless the product has an obvious different demographic), Advantage+ placements.
5. Write ad copy that leads with the bundle offer as a number in the first line, matching the confirmed winning pattern from [`docs/creative-framework.md`](creative-framework.md). Check whether the buyer is the end-user or a parent/gift-buyer, and write to the buyer.
6. If testing both image and video creative, split them into separate ad sets (or guarantee each a minimum ABO budget) — do not let them share one ad set's budget, per the ولاد video-starvation finding.
7. Confirm the landing page's offer copy matches the ad's offer copy exactly (message match) before launch.
8. Let it run. Do not judge it on day 1. Per [`docs/framework.md`](framework.md), a single sale (as with Canton 3's current Tunic test) is not a signal — wait for 2–3 consecutive days of real spend before any Discovery→Validation decision.

## SOP 2 — Decide whether to promote Discovery → Validation

1. Pull daily-level spend, purchases, CPA, and ROAS for the ad set (not lifetime averages).
2. Check: has it produced more than 1 purchase, across more than 1 day?
   - No → still Discovery. Do not act yet.
   - Yes → continue.
3. Is CPA/ROAS trending flat-to-improving across the last 2–3 days of real spend (like ولاد's Mar 3→6 climb, ROAS 16.71x→46.62x)?
   - No, it's declining or erratic → do not promote. Consider a creative or offer rebuild first, using [`docs/decision-tree.md`](decision-tree.md) to diagnose which funnel stage is the problem.
   - Yes → promote to Validation. Do not increase budget yet (see [`docs/framework.md`](framework.md), Stage 2 rules).

## SOP 3 — Scale a validated winner

1. Confirm the ad set has held stable or improving CPA/ROAS at its *current* budget for multiple consecutive days — this is what separates Validation from Scaling.
2. Increase budget (CBO cap or ABO daily budget) by no more than ~20–30%. Do not change targeting, creative, or offer at the same time — isolate the variable (see [`docs/framework.md`](framework.md), Stage 3).
3. Wait 2–3 days before the next increase or any judgment call. A budget increase resets some portion of the learning phase; judging it on day 1 will give a false signal.
4. If ROAS drops sharply after an increase, treat the previous budget level as the ceiling for now — pull back rather than pushing through on hope.
5. If scaling within a CBO campaign, remember: Canton has no direct evidence yet of manual CBO cap increases (ولاد's own scaling was 100% algorithmic auction reallocation, never a manual change) — treat this SOP's step 2 as a framework decision to be validated with real data, not a proven method yet. Record the outcome in [`docs/historical-analysis.md`](historical-analysis.md) once you have it.

## SOP 4 — Weekly audit of all live campaigns

1. Pull every active campaign and ad set across Canton 1/2/3 (whichever accounts have live spend).
2. For each: assign a lifecycle stage explicitly (Discovery / Validation / Scaling / Prime) if not already tagged.
3. Run the relevant sections of [`docs/audit-checklist.md`](audit-checklist.md) against each — do not skip items.
4. For anything underperforming, walk [`docs/decision-tree.md`](decision-tree.md) from the top (CTR first, then LPV, ATC, IC, Purchase) — do not jump to "the audience is wrong" as a first guess (see the decision tree's anti-pattern note).
5. Flag any ad set that has gone dark (zero spend) for more than a few days without a recorded reason — per the ولاد 15-day dark-period finding, a long gap materially damages recovery efficiency, so this needs a deliberate decision, not silent drift.
6. Update [`docs/historical-analysis.md`](historical-analysis.md) with any new confirmed numbers. Do not let new evidence live only in a conversation — if it's not written here, the next agent won't have it.

## SOP 5 — Kill or rebuild a losing ad set

1. First confirm it has actually cleared Discovery-stage spend (see [`docs/framework.md`](framework.md)) — don't kill something that was never given a fair test.
2. Walk [`docs/decision-tree.md`](decision-tree.md) from CTR downward to find which specific funnel stage is failing. Do not kill the whole ad set on a vague "it's not working" — identify the stage.
3. If the problem is Creative (low CTR): rebuild the ad with a bundle-offer-first hook and buyer-matched copy per [`docs/creative-framework.md`](creative-framework.md), before concluding the audience or offer is wrong.
4. If the problem is Offer/ATC: verify the Shopify bundle mechanic is actually firing at checkout, and that pricing is anchored (strike-through) on the page, before concluding the price itself is the issue.
5. If the problem is Checkout/IC→Purchase (Canton's documented biggest and least-understood leak — 78% loss on ولاد's own best ad set): this is very likely NOT a Meta-side fix. Escalate to a Shopify/checkout-flow investigation rather than continuing to iterate on ads — see the open question in [`docs/historical-analysis.md`](historical-analysis.md).
6. Only after ruling out Creative, Offer, and Checkout should Audience/Market be treated as the cause — and even then, remember ولاد's fully broad targeting is the account's best documented result, so "narrow the targeting" is not automatically the right next move.
7. Record the outcome (killed, rebuilt, what changed) in [`docs/historical-analysis.md`](historical-analysis.md)'s Failures & Open Questions section so the next agent doesn't repeat the same dead end.

## SOP 6 — Build or test a new landing page

Follow Canton's own existing, evidenced workflow exactly — see [`docs/landing-page-framework.md`](landing-page-framework.md) for full detail:

1. Duplicate the live product in Shopify.
2. Prefix the duplicate's title with `[LP TEST]`, set status to `DRAFT`.
3. Make copy/layout/imagery changes on the draft only.
4. Preview/test the draft (direct link, or promote to `ACTIVE` under its own handle for a real split test).
5. If the test wins, apply the changes to the live product directly and remove or clearly retire the draft — don't leave two live listings for the same product.
6. Log the result in [`docs/historical-analysis.md`](historical-analysis.md) regardless of outcome — a losing test is still evidence.
