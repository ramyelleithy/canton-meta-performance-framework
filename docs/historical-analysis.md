# Historical Analysis — The Evidence Ledger

This file is the source of truth for every "Canton's data shows X" claim used elsewhere in this repository. If a claim in another file cites a number, that number originates here (or is traceable to a live pull documented here). Update this file whenever a new ad set is fully audited — do not let claims accumulate elsewhere without a corresponding entry here.

## Account map

| Account | ID | Role |
|---|---|---|
| Canton 1 | act_4205438193057243 | Primary historical evidence base — deepest audit trail |
| Canton 2 | act_525502316584543 | Not yet audited in this repository |
| Canton 3 | act_980893808291426 | Current live account — Discovery-stage as of this writing |

## Canton 1 — Top ad sets by spend (account-wide pull)

The ten highest-spend ad sets in Canton 1, ranked, with confirmed metrics. LPV and purchase counts below are directly pulled; ROAS is confirmed for the two fully forensically audited ad sets (#3, #5) and reported as-observed for the others where it was captured during the initial account-wide pull. Where a field wasn't captured, it's left blank rather than guessed — re-pull before citing it as fact.

| # | Ad Set | LPV | Purchases | LPV→Purchase CVR | ROAS |
|---|---|---|---|---|---|
| 1 | US Polo \| Winter \| Old | 2,470 | 100 | 4.0% | — |
| 2 | New Sales Ad Set (بنطلون) | 1,376 | 91 | 6.6% | — |
| 3 | **ولاد** (120240934566540716, campaign "Pants") | 557 | 62 | 11.1% | **23.48x** |
| 4 | New Sales Ad Set (فستان) | 826 | 69 | 8.4% | — |
| 5 | New Sales Ad Set - Apr 2026 | 568 | 59 | 10.4% | **14.28x** |
| 6 | AS \| TS \| Broad \| Purchase | 1,093 | 38 | 3.5% | — |
| 7 | New Sales Ad Set (بنطلون جديد) | 1,252 | 53 | 4.2% | — |
| 8 | New Sales Ad Set - Copy (LC Wideleg) | 1,000 | 51 | 5.1% | — |
| 9 | Men & Women Broad | 1,279 | 59 | 4.6% | — |
| 10 | حريمي 1 | 391 | 35 | 9.0% | — |

**Observation:** the two highest LPV→Purchase conversion rates (#3 ولاد at 11.1%, #5 at 10.4%) are also the two ad sets with confirmed ROAS above 14x — well above the group's ~6.7% average CVR. High funnel-efficiency and high ROAS moved together in this account; raw reach/spend rank (#1, #2) did not predict conversion efficiency. **Rule: when prioritizing which ad sets to study or scale, rank by LPV→Purchase CVR and ROAS, not by spend or LPV volume alone.**

## ولاد — full forensic case study (the account's proven winner)

Full audit performed directly against the Meta API (Canton 1, campaign "Pants", ad set 120240934566540716). This is the deepest evidence in the account and the primary source for the framework's rules.

**Headline numbers:** Lifetime spend EGP2,111.90. Revenue EGP49,584.00. ROAS 23.48x. 62 purchases. CPA EGP34.06 average (ranged EGP16.08 on its best day to EGP77.24 on its worst).

**Timeline:** Created and launched 2026-03-02. First purchase Mar 3 (day 2). Best day Mar 6 — 24 purchases, ROAS 46.62x, CPA EGP16.08. Spend collapsed to zero Mar 8 and stayed dark for 11 straight days (Mar 12–22). A 2-day revival Mar 23–24 never recovered peak efficiency (ROAS 8.78x/9.57x — roughly 5x worse than the Mar 6 peak). Final stop Mar 25.

**Creative:** two ads — a photo/page-post ad ("صور") took 99.66% of spend and 100% of purchases; a video ad ("فيديو") received only EGP7.11 and 49 impressions, never a fair test. Winning copy led with the bundle offer ("3 قطع بـ 799 جنيه") and stated sizing by the wearer's weight/age, written to the buyer (parent), not the wearer (teen).

**Targeting:** fully broad — age 21–65, Egypt, Advantage+ Audience on, no interests, no lookalikes, no gender restriction. Delivery converged on its own: 86% of spend to Female, 69% of spend to age 35–44, 74% of spend to Greater Cairo, 100% of purchases via the mobile app.

**Placement:** Feed carried 90.6% of spend and drove the best ROAS (24.66x) of any placement with real volume; Facebook Reels (9.91x ROAS) and Instagram (essentially untouched, EGP1.40 total) underperformed or were never really tested.

**Time-of-day:** 74% of purchases happened in a 12-hour window, 19:00–06:00 Cairo time — daytime (14:00–18:00) was comparatively dead despite real spend.

**Funnel:** LPV 557 → ViewContent 925 → AddToCart 63 → InitiateCheckout 280 → Purchase 62. Two structural notes: ViewContent exceeding LPV, and InitiateCheckout (4.4x) exceeding AddToCart, both indicate this pixel setup's ATC event under-fires relative to a direct "Order Now"-style checkout flow — treat IC, not ATC, as the reliable mid-funnel signal for Canton's checkout flows. The real leak is IC→Purchase: only 22.1% of checkouts initiated became completed purchases — a 78% drop at the final stage, the single largest gap anywhere in the funnel.

**Full detail:** see the standalone forensic report generated for this ad set (available in the session history this repository was built from) for section-by-section breakdowns (placement, device, age, gender, region, hourly).

## Canton 3 — current strategy (live account, Discovery stage)

As of this writing, Canton 3 runs a single campaign: `Canton | Tunic | ABO | Purchase | EG | V1`, plus a duplicate `V1 - Copy`, each an independent ABO ad set at EGP300.00/day.

| Ad Set | Status | Spend | Purchases | Revenue | ROAS |
|---|---|---|---|---|---|
| Canton \| Tunic \| ABO \| Purchase \| EG \| V1 - Copy | ACTIVE | EGP136.01 | 1 | EGP5.89 | 4.33x |
| Canton \| Tunic \| ABO \| Purchase \| EG \| V1 | PAUSED | EGP77.80 | 0 | — | — |

**Reading this correctly:** this is Discovery-stage data — one purchase at EGP5.89 revenue is not a signal (the revenue figure itself is implausibly low relative to the product's EGP499 price point, which likely means this was a low-value add-on or partial-order capture, not the full tunic order — verify against Shopify order data before drawing any conclusion). Per [`docs/framework.md`](framework.md), this ad set has not yet earned an evaluation of "working" or "not working." Track it forward; don't act on it yet.

**Structural contrast with Canton 1:** Canton 3 uses ABO from the start; Canton 1's proven winner (ولاد) lived inside a CBO campaign. This is a real, documented strategic shift — not yet validated against Canton 1's outcome, since no controlled comparison exists. Track whether Canton 3's ABO Discovery approach reaches Validation faster or slower than Canton 1's CBO-driven ولاد did (which took roughly 4 days of real spend to show a clear signal).

## Shopify — product and offer patterns (live catalog audit)

Confirmed directly from canton-eg.com's product catalog:

- **Bundle mechanics dominate the catalog**: `bundle:2-pieces`, `bundle:3-pieces`, and `offer-bxgy` tags appear across the majority of active and recently-created products (tunic, Boho set, Benetton dress, and others).
- **SKU taxonomy**: `CTN-WM-####` (women), `CTN-KD-####` (kids), `CTN-UN-####` (unisex) — consistent prefix system.
- **Price points cluster tightly**: EGP399–EGP549 across most SKUs reviewed, with the tunic collection at EGP499.
- **Landing-page testing is an active, repeated practice**: three `[LP TEST]`-prefixed DRAFT product duplicates existed at time of audit (Tunic, Boho set, Benetton dress), all created the same day — confirming a live, repeatable LP-testing workflow (see [`docs/landing-page-framework.md`](landing-page-framework.md) for the procedure).
- **Many catalog products sit in DRAFT status with zero inventory** — consistent with a pre-launch/creative-testing phase rather than live selling; do not assume every product in the catalog is currently ad-eligible without checking status and inventory first.

## Failures & open questions (do not fill these in without new evidence)

- **CBO manual scaling was never tested on ولاد.** Its spend growth was 100% algorithmic (CBO auction reallocation), never a manual budget increase. Canton does not have direct evidence of how ولاد would have responded to a deliberate budget increase.
- **Video creative was never fairly tested against photo creative.** The one documented case (ولاد) starved the video ad of delivery (EGP7.11 total) before any real comparison was possible.
- **The 15-day dark period (Mar 8–22) cause is undocumented.** Whether this was a deliberate pause, a budget exhaustion event, or a CBO reallocation to a sibling ad set is not recorded — activity-log access was unavailable at time of audit (Meta API returned "this tool is being gradually rolled out" for this account). If activity-log access becomes available, re-audit this gap specifically.
- **The checkout-completion gap (78% of Initiated Checkouts never became Purchases) has no root-cause data yet.** This is Canton's single biggest documented inefficiency and it currently has zero supporting diagnostic data (no comments data, no checkout-form analytics, no COD-confirmation-call data was available at time of audit). This should be the top investigation priority the next time this repository is updated.
- **Comments/engagement data has never been pulled.** No positive/negative/objection sentiment data exists in this repository for any ad set — flagged as NOT AVAILABLE in the ولاد forensic audit and never subsequently retrieved.
