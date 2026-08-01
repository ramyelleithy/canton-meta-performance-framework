# Canton Meta Performance Framework

This repository is not documentation. It is the operating system for every AI agent and human operator running Meta Ads for Canton Store (canton-eg.com).

## Philosophy

Every rule in this repository traces back to one of two sources:

1. **Historical evidence** — a real number pulled from a real Canton Meta Ads account (Canton 1, act_4205438193057243) or the Canton Shopify store (canton-eg.com).
2. **A framework decision** — a deliberate operating choice made for Canton, recorded here so it doesn't have to be re-litigated every session.

Nothing in here is a paraphrase of Meta's official documentation or a generic "best practice" list. If a statement can't be traced to an ad set, a campaign, a product, or a decision this team actually made, it does not belong in this repository.

## Why this exists

Canton has run three ad accounts (Canton 1, Canton 2, Canton 3) across multiple product lines (pants, tunics, kids sets, dresses) with wildly different naming conventions, budget structures, and outcomes. Canton 1's best-performing ad set ("ولاد", pants campaign) returned a 23.48x ROAS on EGP2,111.90 of spend; other ad sets in the same account never left the launch phase. That gap is not random — it is explained by specific, identifiable choices in targeting, creative, offer structure, and checkout flow. This repository exists so that every future campaign starts from what already worked instead of re-discovering it.

## How AI agents must use this repository

1. **Before building or auditing any campaign**, read [`docs/framework.md`](docs/framework.md) and [`docs/campaign-structure.md`](docs/campaign-structure.md). Do not propose a campaign structure that contradicts the naming convention or lifecycle stage rules defined there without flagging the deviation explicitly to the user.
2. **When performance looks off**, start at [`docs/decision-tree.md`](docs/decision-tree.md). It routes a symptom (low CTR, low LPV, low ATC, low IC, low Purchases) to the correct root-cause category. Do not guess — walk the tree.
3. **When writing or evaluating creative**, use [`docs/creative-framework.md`](docs/creative-framework.md). It documents which angles, offer structures, and copy patterns have real conversion evidence behind them on this account.
4. **When touching the Shopify side** (product pages, offers, checkout), use [`docs/landing-page-framework.md`](docs/landing-page-framework.md). It documents Canton's actual bundle mechanics, trust copy, sizing convention, and landing-page testing workflow — all pulled live from the store, not invented.
5. **Before citing a "winning" pattern**, check [`docs/historical-analysis.md`](docs/historical-analysis.md). It is the evidence ledger. If a claim about "what works for Canton" isn't in there, it needs to be verified against the ad account before it's treated as fact.
6. **Before shipping any new campaign, ad set, or ad**, run it through [`docs/audit-checklist.md`](docs/audit-checklist.md). Every box must be answered, not skipped.
7. **For step-by-step execution** (launching a Discovery test, scaling a winner, auditing a stalled campaign), use [`docs/playbook.md`](docs/playbook.md) — it is the action layer that sits on top of the framework.
8. **Before proposing any change to a framework rule**, read [`docs/evidence-rules.md`](docs/evidence-rules.md) first. It is the constitutional document — it defines what counts as evidence and requires every strategic change to cite [`docs/historical-analysis.md`](docs/historical-analysis.md), [`docs/experiments.md`](docs/experiments.md), or [`docs/winners.md`](docs/winners.md).
9. **When launching or tracking a test**, log it in [`docs/experiments.md`](docs/experiments.md) from day one, using its exact template. Don't wait for the result to write it down.
10. **When a test clears Validation with clear evidence**, add it to [`docs/winners.md`](docs/winners.md). When a test fails — commercially or methodologically — add it to [`docs/failures.md`](docs/failures.md). Both are treated as first-class evidence, not as a record to be cleaned up later.
11. **Before quoting a metric threshold**, check [`docs/kpi-thresholds.md`](docs/kpi-thresholds.md). If a benchmark cell is empty there, treat that metric as undefined for Canton — do not substitute a generic industry number.
12. **If a term's meaning is unclear**, check [`docs/glossary.md`](docs/glossary.md) before guessing at a definition.
13. **Before starting new work**, check [`docs/roadmap.md`](docs/roadmap.md) to see which phase is currently active and what its exit criteria are.
14. **Read [`docs/repository-rules.md`](docs/repository-rules.md) first, before anything else in this repository.** It is the operating constitution — as of v1.2, documentation is complete and this repository is read-only except when updated with new evidence from real experiments (Rule 10). Every future change must satisfy Rules 1–9.

## Repository map

| File | Purpose |
|---|---|
| [`docs/framework.md`](docs/framework.md) | The Discovery → Validation → Scaling → Prime lifecycle and the decision rules that move an ad set between stages |
| [`docs/decision-tree.md`](docs/decision-tree.md) | Symptom → root cause → fix, branching from CTR/LPV/ATC/IC/Purchase |
| [`docs/campaign-structure.md`](docs/campaign-structure.md) | Naming convention, ABO vs CBO rules, hierarchy, creative versioning |
| [`docs/creative-framework.md`](docs/creative-framework.md) | Creative principles, testing workflow, image vs video, hooks/angles/offers with evidence |
| [`docs/landing-page-framework.md`](docs/landing-page-framework.md) | Shopify-side structure: offers, trust, sizing, FAQ, CTA, LP testing method |
| [`docs/historical-analysis.md`](docs/historical-analysis.md) | The evidence ledger — every documented winning/losing pattern from Canton 1 and Canton 3, with numbers |
| [`docs/audit-checklist.md`](docs/audit-checklist.md) | Full pre-launch and in-flight audit checklist across campaign/adset/ad/landing/creative/tracking/pixel/offer/Shopify |
| [`docs/playbook.md`](docs/playbook.md) | Step-by-step SOPs: launch a Discovery test, scale a winner, run a weekly audit, kill a loser |
| [`docs/experiments.md`](docs/experiments.md) | The experiment log — every controlled test, logged from launch to result, using a fixed template |
| [`docs/winners.md`](docs/winners.md) | Every campaign/ad set that cleared Validation with unambiguous evidence — why it won, what must never change, what's still untested |
| [`docs/failures.md`](docs/failures.md) | Every failed test — commercial or methodological — with hypothesis, failure reason, evidence, and whether/how it should be retested |
| [`docs/evidence-rules.md`](docs/evidence-rules.md) | The constitutional document — what counts as evidence, what doesn't, and the citation requirement for every strategic change |
| [`docs/kpi-thresholds.md`](docs/kpi-thresholds.md) | Canton's own performance benchmarks per metric — historical, experimental, and target values, left empty where evidence is insufficient |
| [`docs/glossary.md`](docs/glossary.md) | Every term used across this repository, defined once |
| [`docs/roadmap.md`](docs/roadmap.md) | The Meta Ads operational roadmap — nine phases from repository setup through Prime-stage scaling, each with objective/success/exit criteria |
| [`docs/repository-rules.md`](docs/repository-rules.md) | The operating constitution — the ten rules governing this repository itself, including that documentation is now complete and execution is the focus |
| [`CHANGELOG.md`](CHANGELOG.md) | Version history of the framework itself — every entry must trace to new evidence, not opinion |

## Ground truth accounts

- **Canton 1** — `act_4205438193057243` — the historical evidence base (see [`docs/historical-analysis.md`](docs/historical-analysis.md))
- **Canton 2** — `act_525502316584543`
- **Canton 3** — `act_980893808291426` — current active account, ABO structure, single-product Discovery testing as of this writing
- **Shopify store** — `canton-eg.com`, Basic plan, EGP currency

This repository will be updated as new evidence accumulates. It is never "done" — it is a living record of what Canton's Meta Ads account has actually proven.
