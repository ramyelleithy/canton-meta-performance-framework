# Glossary

Every term used across this repository, defined once, here. If a term is used in another document with a meaning that isn't in this list, add it here rather than letting it drift.

**ABO (Ad Set Budget Optimization)** — a budget structure where each ad set carries its own independent daily budget, rather than sharing one campaign-level budget. Canton 3's current live campaigns use ABO from the start of Discovery so that no single ad set can be starved of spend by a sibling. See [`docs/campaign-structure.md`](campaign-structure.md).

**ATC (Add to Cart)** — the funnel event fired when a visitor adds a product to their cart. On Canton's account, ATC has historically fired less often than IC, suggesting the checkout flow sometimes skips a discrete cart-add step. See [`docs/decision-tree.md`](decision-tree.md) and [`docs/historical-analysis.md`](historical-analysis.md).

**Audit Checklist** — the pre-launch and in-flight verification list covering campaign, ad set, ads, landing page, creative, tracking/pixel, offer, and Shopify. Every box must be answered explicitly before a campaign ships or is judged. See [`docs/audit-checklist.md`](audit-checklist.md).

**Broad (targeting)** — an audience defined with no interest, behavior, or lookalike restrictions — just age, gender, and geography, with Meta's Advantage+ Audience deciding delivery. Canton's only fully forensically audited winner (ولاد) used broad targeting exclusively. See [`docs/campaign-structure.md`](campaign-structure.md) and [`docs/winners.md`](winners.md).

**CBO (Campaign Budget Optimization)** — a budget structure where one daily budget is set at the campaign level and Meta's auction decides how to split it across the campaign's ad sets. Canton 1's "Pants" campaign (home of the ولاد winner) used CBO. See [`docs/campaign-structure.md`](campaign-structure.md).

**CPA (Cost Per Acquisition)** — total spend divided by total purchases for a given ad set or period. Tracked daily, not as a lifetime average, so trend direction is visible. See [`docs/kpi-thresholds.md`](kpi-thresholds.md).

**CPC (Cost Per Click)** — total spend divided by total link clicks. See [`docs/kpi-thresholds.md`](kpi-thresholds.md).

**CPM (Cost Per Mille)** — cost per 1,000 impressions. See [`docs/kpi-thresholds.md`](kpi-thresholds.md).

**Creative** — the actual ad unit shown to a user: an image or video, paired with primary text, and (where available) a headline, description, and call-to-action. Creative principles and testing rules live in [`docs/creative-framework.md`](creative-framework.md).

**CTR (Click-Through Rate)** — the percentage of impressions that resulted in a click. Used as the first diagnostic checkpoint in [`docs/decision-tree.md`](decision-tree.md) — a low CTR points to a creative problem before anything downstream is investigated.

**Decision Tree** — the diagnostic document that routes a specific underperforming metric (CTR, LPV, ATC, IC, Purchases) to its most likely root cause, in order, so problems aren't diagnosed out of sequence. See [`docs/decision-tree.md`](decision-tree.md).

**Discovery** — the first stage of an ad set's lifecycle: the smallest viable spend to find out whether a product/offer/audience combination can convert at all. No scaling or kill decisions are made in this stage on the strength of a single sale or a single day. See [`docs/framework.md`](framework.md).

**Evidence** — a specific, dated, numbered result traceable to a real ad set, campaign, product, or Shopify observation. The only accepted basis for changing any framework rule. Defined formally in [`docs/evidence-rules.md`](evidence-rules.md).

**Evidence Rules** — the constitutional document defining what counts as evidence, what doesn't (Meta documentation alone, YouTube content, community opinion), and the citation requirement for every strategic change. See [`docs/evidence-rules.md`](evidence-rules.md).

**Experiment** — a controlled test with a stated hypothesis, a defined variable that changed, and everything else held constant, logged from launch to result using the fixed template in [`docs/experiments.md`](experiments.md).

**Failure** — a test, commercial or methodological, that did not produce the result its hypothesis predicted. Documented with its hypothesis, execution, results, failure reason, evidence, lesson learned, and whether it should be retested. See [`docs/failures.md`](failures.md).

**Framework** — the overall set of rules and lifecycle stages (Discovery → Validation → Scaling → Prime) that govern how Canton runs and evaluates Meta Ads. Defined in [`docs/framework.md`](framework.md); the term is also used loosely to mean "this repository" as a whole.

**Frequency** — the average number of times a unique person has seen a given ad. Used as an early-warning signal for creative fatigue; Canton's only fully audited winner never exceeded 1.55 lifetime. See [`docs/creative-framework.md`](creative-framework.md) and [`docs/kpi-thresholds.md`](kpi-thresholds.md).

**Glossary** — this document.

**IC (Initiate Checkout)** — the funnel event fired when a visitor begins the checkout process. On Canton's account, treated as the more reliable mid-funnel signal relative to ATC. See [`docs/decision-tree.md`](decision-tree.md).

**Interest (targeting)** — a Meta targeting option that restricts an ad set's audience to people Meta has associated with a stated interest category. No ad set in Canton's documented winners has used interest targeting — all documented winners ran broad. See [`docs/campaign-structure.md`](campaign-structure.md).

**KPI Thresholds** — the single-table reference of Canton's own performance benchmarks per metric, sourced only from historical data, experiments, and winners, with target values left empty until evidence supports one. See [`docs/kpi-thresholds.md`](kpi-thresholds.md).

**LPV (Landing Page View)** — the funnel event fired when a visitor's browser registers a load of the destination landing page after clicking an ad. The first post-click checkpoint in [`docs/decision-tree.md`](decision-tree.md).

**Lookalike (targeting)** — a Meta audience built by finding people who resemble an existing source audience (e.g., past purchasers). Not used in any of Canton's documented winners to date. See [`docs/campaign-structure.md`](campaign-structure.md).

**Playbook** — the step-by-step, action-level SOPs built on top of the framework: launching a Discovery test, promoting to Validation, scaling a winner, running a weekly audit, killing/rebuilding a loser, and testing a landing page. See [`docs/playbook.md`](playbook.md).

**Prime** — the final stage of an ad set's lifecycle: a proven, durable revenue driver that gets protected from casual edits rather than aggressively scaled further. See [`docs/framework.md`](framework.md).

**Purchase Rate** — shorthand used in this repository for LPV→Purchase conversion rate, the ratio of Landing Page Views that ultimately became completed Purchases. See [`docs/kpi-thresholds.md`](kpi-thresholds.md) and [`docs/historical-analysis.md`](historical-analysis.md).

**Roadmap** — the phased, evidence-gated operational plan for Canton's Meta Ads execution, from repository setup through Prime-stage scaling of multiple winning products. See [`docs/roadmap.md`](roadmap.md).

**ROAS (Return On Ad Spend)** — total revenue attributed to an ad set divided by total spend. Canton's headline efficiency metric; ولاد's lifetime ROAS of 23.48x is the account's benchmark case. See [`docs/kpi-thresholds.md`](kpi-thresholds.md).

**Scaling** — the third stage of an ad set's lifecycle: increasing a validated winner's budget in small, isolated increments without changing targeting, creative, or offer at the same time. See [`docs/framework.md`](framework.md).

**Validation** — the second stage of an ad set's lifecycle: confirming a Discovery-stage signal holds at the same spend level across multiple consecutive days before any budget increase is considered. See [`docs/framework.md`](framework.md).

**VC (ViewContent)** — the funnel event fired when a visitor views specific product content, typically corresponding to a product-detail-page view or equivalent. On Canton's account, VC has been observed exceeding LPV, a known measurement artifact rather than a funnel-order violation. See [`docs/historical-analysis.md`](historical-analysis.md).

**Winner** — a campaign or ad set that has cleared Validation with unambiguous evidence of profitable performance, documented with its full offer/audience/creative detail, why it won, what must never change, and a replication strategy. See [`docs/winners.md`](winners.md).

---

**See also:** [`docs/evidence-rules.md`](evidence-rules.md) for how these terms are meant to be used when citing evidence; [`docs/framework.md`](framework.md) for the lifecycle terms (Discovery/Validation/Scaling/Prime) in full context.
