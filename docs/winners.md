# Winners

This file stores every campaign/ad set that has cleared Validation with unambiguous evidence of profitable performance (see the lifecycle stages in [`docs/framework.md`](framework.md)). A "winner" here means a specific, dated, numbered result — not a category of product or a general strategy.

Per [`docs/evidence-rules.md`](evidence-rules.md): this file is one of the three accepted evidence sources for changing anything in the framework docs. If a rule elsewhere in this repository claims something "worked for Canton," the specific winner backing that claim should be findable here.

---

## Winner 1 — ولاد (Boys' Pants)

| Field | Value |
|---|---|
| Product | Boys' pants — Wide-Leg Melton, weight/age-based one-size sizing (35–50kg, ~12–18 years) |
| Campaign | Pants (120240929212100716), CBO, EGP250.00/day |
| Ad Set | ولاد (120240934566540716) |
| Creative | "صور" (photo/page-post ad) — see [`docs/historical-analysis.md`](historical-analysis.md) for full copy |
| Offer | 3 pieces for EGP799 (buy 2, get the 3rd free), stated as the first line of the ad copy |
| Audience | Fully broad — age 21–65, Egypt, Advantage+ Audience on, no interests/behaviors/lookalikes, no gender restriction |
| Budget | EGP250.00/day (CBO, shared across the "Pants" campaign's ad sets) |
| Spend | EGP2,111.90 lifetime |
| Revenue | EGP49,584.00 |
| Purchases | 62 |
| CPA | EGP34.06 average (EGP16.08 best day, EGP77.24 worst day) |
| ROAS | 23.48x lifetime (peaked 46.62x on Mar 6, 2026) |
| CTR | 7.32%–9.49% across active days |
| LPV | 557 |
| ATC | 63 (see note below — likely under-firing relative to IC) |
| IC | 280 |

**Why it won:**
1. Copy was written to the buyer (a mother sizing pants for her teenage son by weight/age), not the end-user — confirmed by delivery data: 86% of spend and 87% of purchases went to Female accounts aged 35–44.
2. The offer was stated as a concrete bundle number ("3 for 799") in the first line, matching Canton's dominant Shopify catalog pattern (see [`docs/landing-page-framework.md`](landing-page-framework.md)).
3. Broad Advantage+ targeting converged tightly on its own onto a specific, efficient buyer segment (Female, 35–44, Greater Cairo, mobile app, night hours) without any manual audience narrowing.
4. Feed placement carried 90.6% of spend at the best ROAS (24.66x) of any placement with real volume.

**What must never change:**
- The bundle offer structure and its position as the first line of the ad copy ("3 for X," not a vague percentage discount).
- Writing sizing/value copy to the buyer (parent), not the end-user, when the product and buyer are different people.
- Broad Advantage+ targeting as the default starting point — this ad set never used interest/behavior/lookalike targeting and still converged efficiently.
- Feed as the primary placement — do not manually restrict away from it without a specific, evidenced reason.

**What can still be tested:**
- Image vs. video creative — never fairly tested here; the video ad was starved of delivery (EGP7.11 of EGP2,111.90 total spend) by running in the same ad set as the stronger-converging photo ad. A real test requires isolated budgets (see [`docs/experiments.md`](experiments.md) EXP-001 and [`docs/creative-framework.md`](creative-framework.md)).
- Manual CBO budget scaling — this ad set's spend growth was 100% algorithmic auction reallocation; Canton has never manually increased a CBO cap on a validated winner to see how it responds (see [`docs/framework.md`](framework.md) Stage 3).
- Dayparting / ad scheduling — 74% of purchases happened in a 12-hour window (19:00–06:00 Cairo time); whether deliberately concentrating budget in that window would improve efficiency further is untested.
- Checkout-flow changes — the IC→Purchase rate was only 22.1% (78% of initiated checkouts never completed), the single largest documented leak in this winner's own funnel. This is the highest-leverage untested lever on this exact winner.

**Replication strategy:**
1. For any new kids'-category product, default to the same weight/age-based one-size sizing and buyer-targeted copy (per [`docs/landing-page-framework.md`](landing-page-framework.md) and [`docs/creative-framework.md`](creative-framework.md)).
2. Launch with the same broad-targeting, bundle-first-offer structure as a Discovery test (per [`docs/playbook.md`](playbook.md) SOP 1) before considering any audience narrowing.
3. Do not replicate the CBO-with-shared-video-and-photo-ad structure — isolate creative format tests this time (log as a new entry in [`docs/experiments.md`](experiments.md)).
4. Treat the checkout-completion gap as a standing hypothesis to test on every replication, not just on this one ad set — see [`docs/decision-tree.md`](decision-tree.md) for the diagnostic path when Purchase is low relative to IC.

---

## Winner 2 (partial) — New Sales Ad Set - Apr 2026

This entry is intentionally incomplete. It qualifies for this file because it is one of only two ad sets in the account-wide top-10 pull with a confirmed ROAS above 14x (see [`docs/historical-analysis.md`](historical-analysis.md)), but it has not yet received the same full forensic audit as Winner 1. Do not treat the blank fields below as zero or as "not applicable" — they are unaudited, not absent.

| Field | Value |
|---|---|
| Product | NOT AVAILABLE FROM META API (not identified in the account-wide pull) |
| Campaign | NOT AVAILABLE FROM META API |
| Ad Set | New Sales Ad Set - Apr 2026 |
| Creative | NOT AVAILABLE FROM META API |
| Offer | NOT AVAILABLE FROM META API |
| Audience | NOT AVAILABLE FROM META API |
| Budget | NOT AVAILABLE FROM META API |
| Spend | NOT AVAILABLE FROM META API |
| Revenue | NOT AVAILABLE FROM META API |
| Purchases | 59 |
| CPA | NOT AVAILABLE FROM META API |
| ROAS | 14.28x |
| CTR | NOT AVAILABLE FROM META API |
| LPV | 568 |
| ATC | NOT AVAILABLE FROM META API |
| IC | NOT AVAILABLE FROM META API |

**Why it won:** LPV→Purchase CVR of 10.4% — the second-highest in the account-wide top-10 ranking, alongside a confirmed ROAS well above the group average. Beyond that, this ad set has not been audited deeply enough to say more without guessing.

**What must never change / What can still be tested / Replication strategy:** PENDING full forensic audit. Do not draw structural conclusions from this entry until it receives the same depth of analysis as Winner 1. Flagged here as a priority for the next audit cycle (see [`docs/playbook.md`](playbook.md) SOP 4).

---

*Add new winners below this line as they clear Validation with full evidence. A partial entry (like Winner 2) is acceptable as a placeholder, but must be clearly marked incomplete — never backfill a blank field with an assumption.*
