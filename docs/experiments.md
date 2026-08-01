# Experiments Log

This is the running log of every controlled test run against a Canton Meta Ads account. Every entry must use the exact template below — no field skipped, no field guessed. If a field can't be filled in yet (test still running, tool access unavailable), write `NOT AVAILABLE FROM META API` or `PENDING` rather than leaving it blank or inventing a number.

An entry belongs in this file the moment a test is launched — do not wait for the result to log it. Update the same entry in place as data comes in; do not create a duplicate entry for the same test.

Per [`docs/evidence-rules.md`](evidence-rules.md): this file, together with [`docs/winners.md`](winners.md) and [`docs/historical-analysis.md`](historical-analysis.md), is one of the three accepted evidence sources for changing anything in the framework docs.

---

## Template

```
### Experiment ID
### Date
### Product
### Campaign
### Ad Set
### Creative
### Hypothesis
### What changed
### What stayed constant
### Budget
### Duration
### Spend
### CTR
### CPC
### CPM
### LPV
### VC
### ATC
### IC
### Purchases
### CPA
### ROAS
### Decision
### Next Action
### Lessons Learned
```

---

## EXP-001

- **Experiment ID:** EXP-001
- **Date:** 2026-03-02 (start)
- **Product:** Boys' pants (bundle: 3 pieces for EGP799)
- **Campaign:** Pants (120240929212100716), CBO, EGP250.00/day
- **Ad Set:** ولاد (120240934566540716)
- **Creative:** Two ads run simultaneously — "صور" (photo/page-post) and "فيديو" (video/page-post), both leading with the same bundle offer copy but different body text (video ad generic/joggers-flavored, photo ad explicitly pants-specific)
- **Hypothesis:** Broad Advantage+ targeting (age 21–65, Egypt, no interests/lookalikes) combined with a bundle-led, weight/age-sized offer will convert boys' pants efficiently without manual audience narrowing.
- **What changed:** This was the ad set's initial launch — targeting, creative, and offer were all new simultaneously (this was not an isolated single-variable test; see Lessons Learned).
- **What stayed constant:** Campaign-level daily budget (EGP250 CBO), attribution setting (1d_view_7d_click_1d_ev), country (EG).
- **Budget:** EGP250.00/day (CBO, shared across ad sets in "Pants" campaign — not a dedicated per-ad-set budget)
- **Duration:** Real spend on Mar 2–7, then dark Mar 8–22, revived Mar 23–24, stopped Mar 25 (see [`docs/historical-analysis.md`](historical-analysis.md) for full daily timeline)
- **Spend:** EGP2,111.90 lifetime (EGP7.11 video ad + EGP2,104.79 photo ad)
- **CTR:** 7.32%–9.49% range across active days (photo ad); 8.16% (video ad, on a 49-impression sample — not statistically meaningful)
- **CPC:** EGP0.51–EGP1.12 range across active days
- **CPM:** EGP44.26–EGP106.08 range across active days
- **LPV:** 557 (lifetime total)
- **VC:** 925 (lifetime total)
- **ATC:** 63 (lifetime total)
- **IC:** 280 (lifetime total)
- **Purchases:** 62 (lifetime total — all 62 from the photo ad; 0 from the video ad)
- **CPA:** EGP34.06 average lifetime (ranged EGP16.08 best day to EGP77.24 worst day)
- **ROAS:** 23.48x lifetime (peaked at 46.62x on Mar 6)
- **Decision:** Confirmed winner — promoted informally to Prime status by virtue of its evidence, though never formally re-scaled after its 15-day dark period. See [`docs/winners.md`](winners.md) for the full winner entry.
- **Next Action:** Replicate the offer/copy/targeting structure on new products per [`docs/playbook.md`](playbook.md) SOP 1; run a properly isolated image-vs-video test next time (see Lessons Learned).
- **Lessons Learned:** This ad set was not a clean single-variable test — creative format (video vs. photo) was never isolated, so the CBO auction starved the video ad (EGP7.11 of EGP2,111.90 total spend, 49 impressions) before it could produce a comparable result. The ad set's overall success is well evidenced, but it cannot be used as evidence that photo beats video — only that the photo creative, as written, worked. Any future format comparison must guarantee a minimum spend floor per creative (separate ad sets or ABO budgets), per [`docs/creative-framework.md`](creative-framework.md).

---

## EXP-002

- **Experiment ID:** EXP-002
- **Date:** 2026-08-01 (start, ongoing as of last audit)
- **Product:** Tunic (تونيك أوفر سايز – كولكشن جديد, EGP499, bundle: 3 pieces / Buy 2 Get 1)
- **Campaign:** Canton | Tunic | ABO | Purchase | EG | V1
- **Ad Set:** two parallel ABO ad sets — `Canton | Tunic | ABO | Purchase | EG | V1` (original) and `...V1 - Copy` (duplicate)
- **Creative:** NOT AVAILABLE FROM META API (not pulled at time of this log entry — creative detail for the Tunic campaign has not yet been audited to the same depth as EXP-001)
- **Hypothesis:** A direct duplicate ad set (same targeting/creative, isolated ABO budget) run in parallel with the original will reveal whether the auction's initial allocation to one ad set over another is a meaningful signal this early, or just auction noise.
- **What changed:** Ad set is duplicated (`- Copy` suffix) with its own independent ABO budget, rather than letting one CBO campaign decide allocation.
- **What stayed constant:** Product, offer, targeting, and (presumably) creative — NOT AVAILABLE FROM META API to confirm creative is identical between the two ad sets.
- **Budget:** EGP300.00/day per ad set (ABO, independent)
- **Duration:** PENDING — still active/early as of last audit; exact day count not available from the snapshot pulled
- **Spend:** EGP136.01 (V1 - Copy, ACTIVE) / EGP77.80 (V1, PAUSED)
- **CTR:** NOT AVAILABLE FROM META API (not pulled in the snapshot used for this entry)
- **CPC:** NOT AVAILABLE FROM META API
- **CPM:** NOT AVAILABLE FROM META API
- **LPV:** NOT AVAILABLE FROM META API
- **VC:** NOT AVAILABLE FROM META API
- **ATC:** NOT AVAILABLE FROM META API
- **IC:** NOT AVAILABLE FROM META API
- **Purchases:** 1 (V1 - Copy) / 0 (V1)
- **CPA:** NOT AVAILABLE FROM META API (one purchase is not enough to compute a stable CPA per [`docs/framework.md`](framework.md))
- **ROAS:** 4.33x (V1 - Copy, on a single EGP5.89 purchase — the revenue figure is implausibly low relative to the EGP499 product price and should be re-verified against Shopify order data, not treated as a real ROAS yet)
- **Decision:** PENDING — still in Discovery stage per [`docs/framework.md`](framework.md). One sale is not a trend. Do not promote, scale, or kill yet.
- **Next Action:** Continue running both ad sets until each has enough purchases to compute a stable CPA/ROAS (per Discovery exit criteria in [`docs/framework.md`](framework.md)); re-pull full funnel data (CTR through IC) before the next audit; verify the EGP5.89 purchase value against the actual Shopify order.
- **Lessons Learned:** PENDING — too early to draw conclusions. This entry exists so the test is tracked from day one, per this file's logging rule, not so it can be judged prematurely.

---

*Add new experiments below this line, oldest first, using the template above. Do not delete or overwrite a prior entry's original data when updating it — append updates with a dated note if the test's status changes materially after this file was last edited.*
