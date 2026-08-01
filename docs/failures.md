# Failures

This file stores tests that did not produce the result the hypothesis predicted — including tests that failed methodologically (bad test design) as well as tests that failed commercially (real spend, no return). Both types matter: a methodology failure wastes the next attempt's time just as much as a commercial one does.

Per [`docs/evidence-rules.md`](evidence-rules.md), a documented failure is still evidence — it is not a category to be quietly deleted or ignored once the framework is updated to avoid repeating it.

**Honesty note:** as of this entry, Canton's account history does not yet contain a cleanly diagnosed *commercial* failure — an ad set that was given a fair Discovery-stage test (per [`docs/framework.md`](framework.md)) and clearly did not work, with full funnel data to explain why. What the account does have is one well-documented *methodology* failure (below) and one *unresolved, still-open* structural failure (the checkout-completion gap, which is a failure that recurs inside otherwise-winning ad sets, not a standalone failed test). Do not fabricate a commercial failure entry to fill this file out — log real ones as they occur.

---

## FAIL-001 — Uncontrolled image-vs-video test inside ولاد

- **Hypothesis:** Running a video ad ("فيديو") and a photo ad ("صور") in the same ad set, both with bundle-led copy, would produce a fair read on which creative format performs better for this product.
- **Execution:** Both ads were launched simultaneously inside the same CBO-funded ad set (ولاد, campaign "Pants," EGP250/day shared budget), with no per-ad spend floor and no isolation between them. See [`docs/experiments.md`](experiments.md) EXP-001 for full detail.
- **Results:** The photo ad received EGP2,104.79 (99.66%) of the ad set's total spend and all 62 purchases. The video ad received EGP7.11 (0.34%) and only 49 impressions — never enough delivery to compute a meaningful CTR, CPA, or ROAS. CTR was nearly identical between the two on the tiny video sample (8.38% photo vs. 8.16% video), which is itself informative: the auction's allocation decision was not obviously driven by a real performance gap.
- **Failure reason:** The test design, not the video creative itself, failed. A CBO/auction environment will lock onto an early leader and compound its advantage before a fair sample exists for the trailing creative. Running two different creative formats in one ad set with a shared budget is not a controlled comparison — it's a race the first mover almost always wins by default.
- **Evidence:** Full spend/impression/purchase breakdown by ad, documented in [`docs/historical-analysis.md`](historical-analysis.md) and [`docs/experiments.md`](experiments.md) EXP-001.
- **Lesson learned:** Never conclude "photo beats video" (or any format-vs-format claim) from an ad set where both formats shared one auction-optimized budget. This lesson is now codified as a standing rule in [`docs/creative-framework.md`](creative-framework.md) ("Image vs. Video" section) and in the [`docs/audit-checklist.md`](audit-checklist.md) Ads section.
- **Should this ever be tested again?** Yes — the underlying question (does video or photo perform better for Canton's products) is still open and commercially important.
  - **If yes, under what conditions:** Each format must get its own ad set (or a guaranteed minimum ABO budget floor within a shared ad set) so both accumulate a comparable sample before either is judged. Log the retest as a new entry in [`docs/experiments.md`](experiments.md), referencing this entry as the reason the test is being run differently this time.

---

## FAIL-002 — The recurring checkout-completion gap (open, not yet resolved)

- **Hypothesis:** N/A — this is not a single test but a pattern observed across the account's best-documented winner, logged here because it represents a real, evidenced failure mode that has not yet been root-caused or fixed.
- **Execution:** N/A — this is observational, drawn from ولاد's funnel data (Winner 1 in [`docs/winners.md`](winners.md)), not a deliberately designed experiment.
- **Results:** Of 280 Initiated Checkouts on ولاد, only 62 became completed Purchases — a 78% drop-off at the final funnel stage, the single largest gap anywhere in that ad set's funnel (LPV 557 → VC 925 → ATC 63 → IC 280 → Purchase 62; see [`docs/historical-analysis.md`](historical-analysis.md)).
- **Failure reason:** UNKNOWN — and that is the point of this entry. No diagnostic data exists yet (no checkout-form analytics, no COD-confirmation-call data, no comments/objections data) to explain why so many initiated checkouts don't convert. This is very likely not a Meta-side problem (creative, targeting, and landing engagement were all strong on this ad set) — see [`docs/decision-tree.md`](decision-tree.md) for the diagnostic path that routes this symptom to Checkout / Trust / Product / Market causes.
- **Evidence:** Funnel numbers documented in [`docs/historical-analysis.md`](historical-analysis.md) and [`docs/winners.md`](winners.md) Winner 1.
- **Lesson learned:** A winning ad set can still contain a large, unexplained internal failure. Don't treat "this ad set worked" as license to stop investigating its weakest stage — the biggest single opportunity in the account right now is inside its best-performing ad set, not in a new one.
- **Should this ever be tested again?** Yes — this is the top open investigation priority in [`docs/historical-analysis.md`](historical-analysis.md) "Failures & Open Questions."
  - **If yes, under what conditions:** This needs a dedicated Shopify/checkout-flow investigation (form length, COD confirmation flow, payment options), not another ad-side experiment. Once root-caused, log the finding here with an update, and log any resulting checkout-flow change as a new entry in [`docs/experiments.md`](experiments.md).

---

*Add new failures below this line as they occur — commercial or methodological. A killed Discovery-stage ad set only belongs here if it was actually given a fair test per [`docs/framework.md`](framework.md); premature kills are not evidence of failure, they're missing data, and should not be logged here as if they were.*
