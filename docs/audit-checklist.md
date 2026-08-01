# Audit Checklist

Run this checklist before launching any new campaign, and again on any campaign that has been live for at least 2–3 days of real spend. Every item must be explicitly answered (yes/no/N/A with a reason) — do not skip items silently. Where an item references a benchmark, the benchmark is sourced from [`docs/historical-analysis.md`](historical-analysis.md).

## Campaign

- [ ] Name follows the convention: `Canton | {Product} | {ABO/CBO} | {Objective} | {Country} | {Version}` (see [`docs/campaign-structure.md`](campaign-structure.md))
- [ ] Objective is OUTCOME_SALES / Purchase-optimized, matching Canton's proven objective on both ولاد and the current Canton 3 Tunic campaign
- [ ] Budget structure (ABO vs CBO) matches the lifecycle stage: ABO for Discovery, CBO only once ad sets have independently cleared Validation (per [`docs/framework.md`](framework.md))
- [ ] Daily budget is at or above the EGP250–300/day floor established by Canton 1 ("Pants," EGP250 CBO) and Canton 3 (EGP300 ABO) — below this floor, Discovery-stage learning will be too slow to read
- [ ] Country targeting confirmed (EG, unless a deliberate new-market test)

## Ad Set

- [ ] Ad set name is segment-descriptive (who/what it tests), not a generic label like "New Sales Ad Set" (Canton 1's documented naming failure — see [`docs/campaign-structure.md`](campaign-structure.md))
- [ ] Targeting is broad by default (Advantage+ Audience on, no interests/behaviors/lookalikes) unless there is a specific, stated reason to narrow — ولاד's only documented full-forensic winner ran fully broad
- [ ] Placements are Advantage+ (automatic) unless a specific placement test is underway — Feed drove 90.6% of ولاد's spend and its best ROAS; don't manually restrict placements without a reason
- [ ] Attribution setting recorded and consistent with prior ad sets in this account (ولاد used 1d_view_7d_click_1d_ev)
- [ ] Lifecycle stage explicitly assigned (Discovery / Validation / Scaling / Prime) — not left implicit
- [ ] If this ad set is a duplicate/copy of another (for a controlled test), confirm it's isolated enough to be measured independently, per the `- Copy` naming pattern

## Ads

- [ ] At least one ad's primary text leads with the bundle offer stated as a number (e.g. "3 for EGP799"), matching the one confirmed winning pattern
- [ ] Copy is written to the actual buyer, not just the end-user — confirm from Shopify data whether this is a parent-buys-for-child situation (as with ولاد) before finalizing tone/angle
- [ ] Sizing is described by weight/age where the product is kids'/unisex, matching Canton's dominant, repeated Shopify pattern
- [ ] If both video and photo formats are being tested, confirm they are NOT sharing a single ad set's budget without a spend floor per ad — ولاد's video ad was starved to EGP7.11 by exactly this mistake
- [ ] Thumbnail/first-frame is not just a static product shot with no offer/hook visible
- [ ] Scarcity/urgency framing, if used, anchors to a real event (season, stock, collection changeover) — not a fabricated countdown

## Landing (Shopify)

- [ ] Message match confirmed: ad copy's stated offer matches the product page's headline offer exactly (both should lead with the same bundle framing)
- [ ] Trust/logistics line present: shipping, COD, exchange/return — Canton's standard block
- [ ] Price shown as a strike-through anchor (was/now), not just a flat price
- [ ] Bundle mechanic stated as "applies automatically at checkout" if that's how it's implemented — don't leave the mechanic ambiguous
- [ ] Page tested on a mobile in-app webview specifically, not just a standard mobile browser — 100% of ولاد's purchases came through the native app webview
- [ ] If this is a new/changed page, was it built as a `[LP TEST]` draft duplicate first, per Canton's existing testing workflow, rather than edited live?

## Creative

- [ ] CTR being tracked daily against the 7% floor (ولاد's lowest daily CTR on a real-spend day was 7.32%)
- [ ] Frequency being tracked against the ~2.0 watch threshold (ولاد never exceeded 1.55 lifetime)
- [ ] No single ad set has been dark (zero spend) for more than a few days without an explicit decision recorded — ولاد's 11-day dark gap and subsequent failure to recover efficiency is the account's clearest cautionary case
- [ ] Creative refreshes on Prime-stage ad sets are staged/rotated, not a sudden full swap

## Tracking / Pixel

- [ ] Confirm which pixel event is mapped to "Purchase" in Ads Manager — this repository could not confirm the pixel ID or exact custom-event name during the ولاد audit (NOT AVAILABLE FROM META API via this tool); verify directly in Events Manager before relying on optimization signal quality
- [ ] Confirm whether AddToCart is firing as a discrete event or being skipped in favor of a direct "Order Now"-to-InitiateCheckout flow — ولاد showed IC (280) far exceeding ATC (63), meaning ATC is likely not a reliable signal for this account's checkout flow
- [ ] If IC is being used as the primary mid-funnel proxy (recommended, given the above), confirm this decision is documented on the ad set/campaign, not just assumed
- [ ] Attribution window confirmed and consistent across ad sets being compared (don't compare a 1-day-click ad set against a 7-day-click one)

## Offer

- [ ] Offer is stated as a concrete number (e.g. "3 for 799," "buy 2 get 1 free"), not a vague percentage or "sale"
- [ ] Offer matches an active Shopify bundle mechanic (`bundle:2-pieces`, `bundle:3-pieces`, `offer-bxgy`, etc.) that actually applies at checkout — verify the tag exists and the discount fires, don't assume from the ad copy alone
- [ ] Price point sits within Canton's proven range (EGP399–EGP549 cluster observed across the catalog) or has a specific reason to deviate

## Shopify

- [ ] Product status is ACTIVE (not DRAFT) before any ad traffic is sent to it — several catalog products were found in DRAFT status with zero inventory at time of audit; confirm before launch, don't assume
- [ ] Inventory is non-zero for the sizes/colors being advertised — multiple SKUs in the catalog showed 0 inventory on specific variants
- [ ] SKU prefix matches the product category correctly (`CTN-WM-`, `CTN-KD-`, `CTN-UN-`) for correct reporting/reconciliation
- [ ] If this product page was built from a `[LP TEST]` draft, confirm the winning version has been merged into the live product and the draft has been cleaned up or clearly marked as superseded

---

**See also:** [`docs/experiments.md`](experiments.md) for logging the test this checklist is gating; [`docs/winners.md`](winners.md) and [`docs/failures.md`](failures.md) for the evidence this checklist's benchmarks are drawn from; [`docs/evidence-rules.md`](evidence-rules.md) for how those benchmarks may be changed.
