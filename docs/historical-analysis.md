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

---

## Historical Pattern Discovery v1

This section documents the account's first systematic DNA-discovery pass: the top 5 campaigns, top 5 ad sets, and top 5 ads in Canton 1's full history (`date_preset=maximum`), ranked independently at each level by Purchases → ROAS → CPA → Purchase Value → Spend, compared variable by variable. Full methodology, per-winner data tables, and the complete confidence-classification report are preserved in this repository's session record; this section captures only the findings themselves, with confidence levels, so they can be cited going forward.

Confidence bands used throughout: **Confirmed** (≥80% of the sample), **Likely** (60–79%), **Experimental/Unconfirmed** (<60% or contradictory), **Unknown** (not retrievable from the Meta API at all).

### Top recurring campaign structure

**CBO — Confirmed (80%, 4/5 top campaigns).** Archived \| US Polo \| CBO \| EG, بنطلون, Pants, and فستان all ran Campaign Budget Optimization; only one of the top 5 (`ABO \| Purchase \| Discovery`) used ABO. **This directly conflicts with the existing Discovery-stage default in [`docs/framework.md`](framework.md) and [`docs/campaign-structure.md`](campaign-structure.md), which recommend ABO.** The conflict is recorded here rather than silently resolved — see the Historical Evidence section added to `docs/framework.md` and the reconciliation note in [`docs/hypotheses.md`](hypotheses.md).

### Top recurring audience

**Broad targeting — Confirmed (100%, 5/5 top ad sets).** US Polo \| Winter \| Old, the بنطلون and فستان ad sets, ولاد, and New Sales Ad Set - Apr 2026 (Benetton) all ran with zero interest, lookalike, custom-audience, or retargeting layers. **Advantage Audience ON with full age+gender expansion — Confirmed (100%, 5/5).** **No manual gender restriction — Confirmed (100%, 5/5).** **Country = EG — Confirmed (100%, 5/5).** **Age range 18–65 — Confirmed (80%, 4/5; the fifth, ولاد, used 21–65).** Languages: NOT AVAILABLE FROM META API — no explicit locale targeting was set or returned on any of the 5.

### Top recurring placements

**Automatic (Advantage+) placements — Confirmed (100%, 5/5).** All five top ad sets carried identical `effective_publisher_platforms` (Facebook, Instagram, Audience Network, Messenger, Threads) with no manual placement restriction. Per-placement purchase breakdown is available at this depth only for ولاد (documented above: Feed carried 90.6% of spend at the best ROAS) — not independently re-verified for the other 4 in this pass.

### Top recurring attribution

**`1d_view_7d_click_1d_ev` — Confirmed (100%, 5/5).** Every top-5 ad set, spanning December 2025 through March 2026 and four different product lines, used the identical attribution window. This is the single most uniform variable found anywhere in the account.

### Top recurring optimization

**OFFSITE_CONVERSIONS (Purchase) — Confirmed (100%, 5/5).** No top-5 ad set used Highest Volume, Cost Cap, Bid Cap, or a ROAS-goal (VALUE) optimization.

### Top recurring creative type

**STATUS / existing Page Post — Confirmed (100%, 5/5 top ads).** New Sales Ad (US Polo), New Sales Ad (بنطلون), صور (ولاد), Album (Men & Women Broad), and New Sales Ad - Copy (بنطلون جديد) were all boosted from an existing Page Post (`object_type: STATUS`), not a freshly-built image/video/carousel/collection/dynamic-creative ad unit. No image, video, carousel, collection, or dynamic-creative format cleared the account-wide top-5-ads threshold. **Caveat:** this may partly reflect that Canton runs STATUS-format ads far more often than other formats — frequency-of-use is a confound this pass cannot rule out. The one video-format ad found near winner tier (`DCT \| TS \| 3 Videos`, 38 purchases) fell short of the weakest top-5 ad (50 purchases), but n=1 is not enough to conclude video underperforms — see [`docs/failures.md`](failures.md) FAIL-001, which already documents that video has never been given a fair, isolated test at this account.

### Top recurring creative origin

**Existing Page Post (object_story_id present) — Confirmed (100%, 5/5).** Whether each of these posts was published organically to the Page timeline first ("boosted post") or created directly as an ad-only story is **NOT AVAILABLE FROM META API** — the tool cannot distinguish "existing post reused" from "dark ad with a story ID" from the fields it returns. This sub-distinction is Unknown, even though "Existing Page Post" as a category is Confirmed.

### Top recurring CTA

**Unknown — 0/5 determinable.** No `call_to_action_type` was returned for any of the top-5 ads' creatives. The only CTA value observed anywhere near winner tier was `SHOP_NOW`, on the single video-format ad mentioned above (n=1, not a pattern).

### Top recurring hook patterns

**Insufficient data — Unknown/Experimental.** Full primary-text body was retrievable for only 2 of the top 5 ads (صور/ولاد and Album/Men & Women Broad); the other 3 (US Polo, بنطلون, بنطلون جديد-Copy) returned an empty `body` field — the copy lives on the underlying Page post and is NOT AVAILABLE FROM META API through this tool. Of the 2 with visible text, they **disagree**: ولاد led with a bundle offer ("3 قطع بـ799... اشتري قطعتين وخدي الثالثة هدية"), matching the pattern already documented in [`docs/creative-framework.md`](creative-framework.md); Album led with a pain-point hook ("زهقت من البنطلونات الضيقة") and never mentioned a bundle. n=2 is too small to generalize — do not treat the bundle-first rule as account-wide confirmed; treat it as confirmed only for the product categories it's actually been observed in (kids'/dress category, per ولاد and the Benetton winners in [`docs/winners.md`](winners.md)).

---

**See also:** [`docs/experiments.md`](experiments.md) for the day-by-day experiment log this analysis is drawn from; [`docs/winners.md`](winners.md) and [`docs/failures.md`](failures.md) for the account's confirmed winners and failures in their standardized templates; [`docs/evidence-rules.md`](evidence-rules.md) for what qualifies as evidence in the first place; [`docs/hypotheses.md`](hypotheses.md) for these findings restated as testable hypotheses with next-experiment recommendations.
