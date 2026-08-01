# Creative Framework

## Creative principles — evidence, not theory

Every principle below is backed by a specific number pulled from Canton 1's account. Where Canton doesn't yet have evidence, it's marked as an open question rather than filled in with a generic claim.

### 1. Copy must speak to the buyer, not the wearer

ولاد's winning ad copy (the "صور" ad, EGP2,104.79 of EGP2,111.90 total spend, 62 of 62 purchases) sold boys' pants by describing sizing in terms of the *child's* weight and age: "يلبس من وزن 35 لحد 50 كيلو (تقريبًا من سن 12 لـ 18 سنة)" — "fits weight 35 to 50 kg (roughly ages 12 to 18)." The delivery data confirms this worked exactly as written: 86% of spend and 87% of purchases went to **Female** accounts aged **35–44** — mothers, not teenage boys. The copy was never written to persuade a 15-year-old to click an ad; it was written to answer a mother's practical sizing question. **Rule: when the buyer and the end-user are different people (kids' products bought by parents), write the copy to the buyer's decision criteria (sizing certainty, practicality, value), not to the end-user's taste.**

### 2. The offer needs to be stated early and stated as a bundle

Both of ولاد's ad texts opened with the offer, not the product: "3 قطع بـ 799 جنيه بس 🔥 ... اشتري قطعتين… وخدي الثالثة هدية 🎁" (3 pieces for EGP799 — buy 2, get the 3rd free) — this is the first line of both creatives, before any product description. Shopify's current live catalog confirms this isn't a one-off: nearly every active/recent product carries a `bundle:2-pieces`, `bundle:3-pieces`, or `offer-bxgy` tag, and the product description repeats the same "buy X get Y free/discounted" structure with an explicit "يتطبق تلقائيًا عند الدفع" (applied automatically at checkout) reassurance. **Rule: lead creative copy with the bundle offer, stated as a number ("3 for 799"), not a percentage or vague "sale."**

### 3. CTR range to benchmark against

ولاد's daily CTR ran 7.32%–9.49% across its full active period, never dropping below 7% on a day with real spend. Use **7% as the floor** for a Canton creative that's actually working — materially below that on a fair sample size (not day-1 noise) is a creative probland, per the decision tree.

### 4. Frequency ceiling before fatigue

ولاد never exceeded a lifetime frequency of 1.55 (photo ad) — and its worst-efficiency days (Mar 23–24 revival, ROAS 8.78x/9.57x vs. 46.62x peak) came not from frequency fatigue (frequency was still low, 1.10/1.05) but from a 15-day dark gap breaking continuity. Canton does not yet have direct evidence of what frequency level causes fatigue on this account — treat frequency above ~2.0 as a watch threshold, not a confirmed kill threshold, until evidence exists.

## Image vs. Video

**Evidence is asymmetric, and that's the finding itself.** In the ولاد ad set, the photo-based ad ("صور") received EGP2,104.79 (99.66%) of spend and all 62 purchases; the video ad ("فيديو") received EGP7.11 (0.34%) and 49 total impressions — never enough delivery to prove or disprove anything. CTR was nearly identical between the two (8.38% photo vs. 8.16% video) on the tiny video sample, which means **the auction did not starve the video ad because it performed worse — it starved it because the photo ad converted first and captured the CBO auction's attention.**

**Rule: never run a video and photo ad in the same ad set expecting a fair test.** The CBO/auction mechanic will pick an early leader and compound its advantage before either creative has a meaningful sample. If Canton wants a real image-vs-video answer, each format needs its own ad set (or its own ABO budget floor) so both get guaranteed minimum spend before a winner is declared.

## Hooks, angles, offers — what's proven vs. untested

| Element | Status | Evidence |
|---|---|---|
| Bundle offer stated in the first line ("3 قطع بـ 799") | **Proven** | ولاد, both ads, EGP49,584 revenue on EGP2,111.90 spend |
| Weight/age-based sizing stated explicitly | **Proven** | ولاد copy + Shopify catalog pattern (repeated across Boho set, Benetton dress, tunic products) |
| Seasonal/occasion framing (ولاد used "لحد آخر رمضان فقط" — Ramadan deadline) | **Proven directionally** | Can't isolate its individual contribution from the bundle offer, but it was present on the winning creative and creates urgency without discounting further |
| Emoji-led bullet structure (✔/🎁/🚚/💵) | **Proven directionally** | Present on both ولاد ads and every Shopify product description reviewed — consistent house style, not verified in isolation as a CTR driver |
| Video-first creative strategy | **Untested** — starved of delivery in the one documented case | Do not conclude video underperforms; conclude it was never fairly tested |
| Narrow interest/behavior targeting as a creative lever | **Not applicable / untested** | ولاد ran fully broad; no Canton ad set has documented interest-targeting creative pairing to compare against |

## Creative testing workflow (framework decision)

1. **Isolate the format test.** Never put a video and an image ad head-to-head in the same ad set if you actually want to compare them — split into separate ad sets or guarantee a minimum ABO spend per ad, per the Image vs. Video finding above.
2. **Lead every new creative with the offer**, matching the proven "3 for X" bundle-lead structure, unless deliberately testing a different opening as a controlled variant.
3. **Match copy to the buyer, not just the product category.** Before writing kids'-product copy, confirm from Shopify's product data whether the buyer is likely the parent (as with ولاد) — if so, write sizing and value language a parent would search for.
4. **Track CTR against the 7% floor and frequency against the ~2.0 watch threshold daily**, not as a lifetime average, so fatigue or a weak hook is caught while there's still budget to react.
5. **Don't judge a creative that hasn't cleared Discovery-stage spend** (see [`docs/framework.md`](framework.md)) — a single day or a single sale (as with Canton 3's current Tunic test, one EGP5.89 purchase so far) is not evidence of anything yet.

---

**See also:** [`docs/winners.md`](winners.md) for the full winner entries these creative principles are drawn from; [`docs/failures.md`](failures.md) FAIL-001 for the uncontrolled image-vs-video test and why it doesn't count as evidence either way; [`docs/experiments.md`](experiments.md) for logging any new creative test.
