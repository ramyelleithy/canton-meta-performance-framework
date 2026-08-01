# The Canton Meta Ads Framework

Every ad set Canton runs sits in exactly one of four lifecycle stages: **Discovery → Validation → Scaling → Prime**. The stage determines the budget, the patience threshold, and what "success" is allowed to mean. Do not evaluate a Discovery-stage ad set by Prime-stage standards, and do not leave a proven Prime-stage winner sitting at Discovery budget.

## Stage 1 — Discovery

**Purpose:** find out if a product/offer/audience combination can convert at all, with the smallest possible spend.

**Evidence this stage matters:** Canton 3's current live campaign, `Canton | Tunic | ABO | Purchase | EG | V1`, is a single ad set at EGP300/day testing one product (Tunic) with a duplicate ad set (`V1 - Copy`) running in parallel. After EGP136.01 and EGP77.80 respectively, one ad set had produced a single EGP5.89 purchase (ROAS 4.33x on a single sale — not yet a real signal) and the other had zero purchases. This is exactly what Discovery is supposed to look like: cheap, fast, inconclusive on day one, and not yet a basis for any scaling decision.

**Rules:**
- Budget: minimum viable daily budget (Canton 3's current floor is EGP250–300/day, matching Canton 1's "Pants" campaign CBO budget of EGP250/day).
- Duration: give it enough spend to pass the learning phase (Meta's own ~50 conversions/week threshold is a floor, not a target — Canton's own ad sets converted on far fewer purchases than that before a clear signal appeared; see `historical-analysis.md` for the ولاد timeline, where the first real signal appeared by day 3–4 of spend, not day 7).
- Decision rule: an ad set stays in Discovery until it has enough purchases to compute a stable CPA/ROAS — not zero, not one. One sale is not a trend (see the Tunic example above).
- Exit criteria: promote to Validation if CPA/ROAS trend is positive across at least 2–3 consecutive days of real spend; kill or rebuild (new creative/offer/audience) if CTR, LPV, or IC never move after a fair test.

## Stage 2 — Validation

**Purpose:** confirm the Discovery signal holds under slightly more spend and isn't a one-off cluster of lucky purchases.

**Evidence this stage matters:** ولاد's own trajectory shows the difference between a lucky day and a real signal. Day 1 (Mar 2) had zero conversions. Day 2 (Mar 3) produced the first 3 purchases at ROAS 16.71x. By day 4 (Mar 6) it hit 24 purchases at ROAS 46.62x, CPA EGP16.08 — the actual proof point. A team that had judged this ad set on day 1 or even day 2 alone would have had an incomplete picture; a team that judged it by day 4 had real evidence.

**Rules:**
- Do not increase budget yet. Validation confirms the signal is repeatable at the *same* spend level, not a bigger one.
- Track ROAS and CPA day-by-day, not as a lifetime average — a lifetime average hides whether the ad set is trending up or down.
- An ad set that is flat or declining across Validation (see ولاد's Mar 23–24 revival at ROAS 8.78x/9.57x — roughly 5x worse than its Mar 6 peak) should not be scaled on the strength of its earlier numbers. Past performance inside the same ad set does not carry forward automatically.

## Stage 3 — Scaling

**Purpose:** take a validated winner and increase its share of budget without breaking what made it work.

**Evidence this stage matters:** ولاد never had a manual per-ad-set budget — it lived inside a CBO campaign at a fixed EGP250/day cap, and its spend moved entirely because Meta's auction reallocated more of that fixed budget toward it as ROAS climbed (Mar 4→6: spend EGP415→574→386 while ROAS climbed 17.9x→23.6x→46.6x). That is CBO doing exactly what it's supposed to do — but it also means Canton 1 never tested what a *manual* CBO cap increase or a dedicated ABO scaling ad set would have done. That's an open question, not a known answer — see `historical-analysis.md` "Failures & Open Questions."

**Rules:**
- Scale budget, not structure, first: raise the CBO cap or the ABO daily budget by no more than ~20–30% at a time, and give each increase 2–3 days to re-stabilize before the next increase. (Framework decision — Canton 1 does not have direct evidence of the ideal increment size, since it never manually scaled ولاد.)
- Do not touch targeting, creative, or offer while scaling budget. Isolate the variable.
- If ROAS drops sharply after a budget increase, the previous budget level was the actual ceiling for that audience — pull back, don't push through.
- Duplicating a winning ad set into a fresh ad set (to reset the auction/audience) is a valid scaling lever but was never used on ولاد — treat as untested until Canton 3 evidence exists.

## Stage 4 — Prime

**Purpose:** the ad set/campaign is a proven, durable revenue driver and gets protected, not just scaled.

**Rules:**
- A Prime ad set should not be edited casually (creative refresh, budget change, targeting tweak) without a documented reason — every edit resets some portion of the learning phase and risks the exact efficiency curve that got it here.
- Prime ad sets get creative refreshes on a rotation, not a sudden swap, to avoid the kind of drop ولاد saw after its 15-day dark period (Mar 8–22) — when it came back Mar 23, it never recovered its Mar 6 efficiency. **Long pauses on a proven ad set are expensive**: this is the single clearest lesson from Canton 1's evidence.
- No ad set in Canton's history (Canton 1 or Canton 3, as of this writing) has been tracked long enough end-to-end to have hard Prime-stage rules beyond "protect it and don't let it go dark." This section should be expanded the first time an ad set demonstrably reaches Prime and is tracked through a full lifecycle.

## Decision Rules Summary

| Situation | Rule |
|---|---|
| Ad set has <1 day of real spend | Still in Discovery — no decisions yet |
| Ad set has spend but 0–1 purchases | Still in Discovery — one sale is not a trend (Canton 3 Tunic evidence) |
| Ad set shows 2–3 consecutive days of stable/improving CPA | Promote to Validation |
| Ad set holds its CPA/ROAS at the same budget for several days | Eligible for Scaling |
| Ad set's budget was just increased | Freeze all other variables for 2–3 days before judging the result |
| Ad set goes dark (zero spend) for more than a few days | Treat re-activation as a new Discovery test, not a continuation — do not assume it will re-hit its prior efficiency (ولاد evidence: post-pause ROAS was ~5x worse than its peak) |
| Ad set is a proven Prime performer | Protect delivery continuity above all else; no casual edits |

See [`docs/decision-tree.md`](decision-tree.md) for what to do when a specific metric (CTR, LPV, ATC, IC, Purchases) is the problem, independent of lifecycle stage.

---

**See also:** every promotion/scaling/kill decision made under this lifecycle should be logged as a dated entry in [`docs/experiments.md`](experiments.md); confirmed winners belong in [`docs/winners.md`](winners.md) and confirmed failures in [`docs/failures.md`](failures.md). Any change to the rules above requires evidence per [`docs/evidence-rules.md`](evidence-rules.md).
