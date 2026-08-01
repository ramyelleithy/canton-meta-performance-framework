# Experiments Roadmap

This is the prioritized queue of the next controlled tests Canton should run, generated directly from the open items in [`docs/hypotheses.md`](hypotheses.md) and the Historical Pattern Discovery findings in [`docs/historical-analysis.md`](historical-analysis.md). Every experiment below isolates exactly **one** variable — this is a direct, structural fix for the mistake already documented in [`docs/failures.md`](failures.md) FAIL-001, where an uncontrolled multi-variable test produced unusable evidence.

Per [`docs/evidence-rules.md`](evidence-rules.md) Rule 8 (historical replication must precede optimization), **EXP-003 must run and be evaluated before any of the experiments after it.** The rest are ordered by priority, but none of them are valid to launch until EXP-003 has confirmed that Canton's best-documented historical pattern still reproduces under current conditions.

Every experiment logged here should be opened as a live entry in [`docs/experiments.md`](experiments.md), using its exact template, the moment it actually launches — this document is the plan; `docs/experiments.md` is the record of what happened.

---

## EXP-003 — Historical Replication

**Priority: 1 (must run first, blocks everything below it)**

- **Objective:** Reproduce the best historical Benetton campaign with the highest possible fidelity.
- **Source winner:** "Dress Benetton" campaign (`120241892188300716`) → ad set "New Sales Ad Set - Apr 2026" (`120241892188310716`) — ROAS 14.28x, 59 purchases, EGP3,312.44 spend, documented as Winner 2 in [`docs/winners.md`](winners.md).
- **Variables changed:** **None.**
- **What must be reproduced exactly:**
  - Campaign structure: **CBO**, not ABO (the original ran CBO — do not "correct" this to ABO before EXP-003 has run, even though current framework guidance defaults to ABO; that conflict is exactly what this replication is meant to test the ground under, per `docs/framework.md` "Historical Evidence (v1.3)")
  - Budget: EGP300.00/day, matching the original
  - Targeting: broad, age 18–65, EG (home + recent), Advantage Audience ON with full age/gender expansion, no interest/lookalike/custom layer
  - Placements: fully automatic (Advantage+)
  - Optimization goal: OFFSITE_CONVERSIONS
  - Attribution: `1d_view_7d_click_1d_ev`
  - Creative: the same two winning STATUS/Page-Post ads — "صور الطبيعه" (30 purchases, ROAS 16.06x, CPA EGP48.61) and "صور بنات" (29 purchases, ROAS 12.88x, CPA EGP63.93) — reused as-is, not rebuilt, not rewritten
  - Same destination product (Benetton dress, `canton-eg.com/products/benetton-premium-cotton-dress-girls`)
- **What stays constant:** everything. This is the point of a replication test — if the reproduction doesn't come close to the original's numbers with zero variables changed, that's itself the finding, and it means external conditions (season, price, competition, algorithm changes) have shifted enough that historical confidence levels across the whole repository need to be re-examined before any of them are trusted for new decisions.
- **Decision rule:** compare CPA and ROAS trend against the original's Mar 27 – onward trajectory (documented in `docs/historical-analysis.md`). If it reproduces within a reasonable range, EXP-006 (CBO vs. ABO) becomes valid to run next. If it does not reproduce, treat every "Confirmed" finding in `docs/hypotheses.md` as provisionally downgraded until the cause of the drift is understood.
- **Log as:** a new entry in [`docs/experiments.md`](experiments.md) the moment it launches.

---

## EXP-004 — Existing Post vs. Dark Ad

**Priority: 2**

- **Hypothesis tested:** HYP-003 (`docs/hypotheses.md`) — existing Page Posts outperform dark-built creative.
- **Objective:** Determine whether the account-wide 100% dominance of STATUS/Page-Post creative among top-5 ads (`docs/historical-analysis.md` "Top recurring creative type") reflects real performance superiority, or just reflects that Canton has almost never built a dark ad at comparable spend.
- **Variable changed:** creative origin only — one ad set runs a reused Page Post (STATUS), a second, otherwise identical ad set runs a freshly-built dark creative (direct `image_hash`/`video_id`, no underlying organic post) with matching offer copy and destination.
- **What stays constant:** product, offer, targeting, budget, placements, optimization goal, attribution — everything except the creative's origin.
- **Why priority 2:** this is the most repeated, least-tested pattern in the entire account (100% confirmed by frequency, 0% confirmed by head-to-head comparison).

---

## EXP-005 — Image vs. Video

**Priority: 3**

- **Hypothesis tested:** HYP-004 — images outperform videos.
- **Objective:** Run the image-vs-video comparison that FAIL-001 documents as never having been fairly tested — this time with each format given its own isolated ad set and a guaranteed minimum spend floor, exactly as the corrective rule in [`docs/creative-framework.md`](creative-framework.md) already specifies.
- **Variable changed:** creative format only (image vs. video), with matching offer copy, targeting, budget, and destination held constant across two separate ad sets.
- **Why priority 3:** second-most-repeated unresolved question in the account; already has a documented failed attempt to learn from (FAIL-001), so the test design is already de-risked.

---

## EXP-006 — Broad vs. Women 25–44

**Priority: 4**

- **Hypothesis tested:** an implicit assumption underlying HYP-001/HYP-005 — that broad, Advantage-Audience-expanded targeting is better than a manually narrowed demographic, even though Canton has occasionally used narrower targeting (e.g., the historical `AS \| Benetton Set \| Broad \| DCT` ad set ran age 25–45, female-only, and still produced 14 purchases at ROAS 3.92x — a real but weaker result than the account's broad winners).
- **Objective:** Directly compare a broad, Advantage-Audience ad set against a hard-capped Women 25–44 ad set, same product, same creative, same budget.
- **Variable changed:** audience definition only (broad + Advantage Audience vs. manually capped Women 25–44, Advantage Audience off).
- **Why priority 4:** depends on EXP-003 confirming the account's current environment still behaves like its history before spending budget testing a targeting variable on top of possibly-stale assumptions.

---

## EXP-007 — Automatic vs. Manual Placements

**Priority: 5**

- **Hypothesis tested:** HYP-002 — automatic (Advantage+) placements outperform manual placement selection.
- **Objective:** Test whether restricting delivery to the placements that have historically converted best (Feed, per the ولاد placement breakdown in `docs/historical-analysis.md`) outperforms, underperforms, or matches full automatic placement.
- **Variable changed:** placement setting only (Advantage+ automatic vs. a manual placement list built from ولاد's own top-converting placements).
- **Why priority 5:** automatic placement is 100% confirmed by frequency across the account, but — like HYP-002 and HYP-005 — that's confirmation-by-absence, not confirmation-by-contrast. Lower priority than EXP-004/005/006 because there's no evidence of manual placement ever failing here; there's just no evidence of it having been tried.

---

## EXP-008 — Attribution Comparison

**Priority: 6**

- **Hypothesis tested:** HYP-006 — `1d_view_7d_click_1d_ev` outperforms other attribution models.
- **Objective:** Test the default attribution window against an alternative (e.g., 7-day click only, no view-through) on otherwise identical ad sets, to determine whether the account's 100%-uniform attribution setting reflects a real advantage or simply reflects that it's never been varied.
- **Variable changed:** attribution window only.
- **Why priority 6 (lowest of the numbered queue):** this variable has produced zero internal disagreement to investigate (100% uniform across every ad set ever pulled), and attribution windows mostly affect *measurement* of results rather than *delivery* of them — lower expected impact on actual purchase volume than EXP-004 through EXP-007, so it's queued last.

---

## Priority summary

| Priority | Experiment | Variable Isolated | Blocks |
|---|---|---|---|
| 1 | EXP-003 | None (pure replication) | Everything below it, per Evidence Rule 8 |
| 2 | EXP-004 | Creative origin (Page Post vs. dark ad) | — |
| 3 | EXP-005 | Creative format (image vs. video) | — |
| 4 | EXP-006 | Audience (broad vs. Women 25–44) | — |
| 5 | EXP-007 | Placements (automatic vs. manual) | — |
| 6 | EXP-008 | Attribution window | — |

**See also:** [`docs/hypotheses.md`](hypotheses.md) for the full hypothesis each experiment resolves; [`docs/experiments.md`](experiments.md) for logging each experiment once it actually launches; [`docs/failures.md`](failures.md) FAIL-001 for the design mistake this roadmap's one-variable-per-test rule directly corrects; [`docs/evidence-rules.md`](evidence-rules.md) Rule 8 for why EXP-003 gates every experiment after it; [`docs/playbook.md`](playbook.md) SOP 1 for the launch procedure each experiment should follow.
