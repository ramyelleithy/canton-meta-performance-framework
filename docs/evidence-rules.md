# Evidence Rules

This is the constitutional document of the Canton Meta Performance Framework. Every other file in this repository operates under these rules. If a proposed change to any framework document conflicts with this file, this file wins.

## 1. The framework must never change because of opinions.

No document in this repository — [`docs/framework.md`](framework.md), [`docs/decision-tree.md`](decision-tree.md), [`docs/campaign-structure.md`](campaign-structure.md), [`docs/creative-framework.md`](creative-framework.md), [`docs/landing-page-framework.md`](landing-page-framework.md), or [`docs/audit-checklist.md`](audit-checklist.md) — may be edited on the strength of "I think," "it feels like," "usually," or "in my experience." A change made this way is not a framework update; it's noise that will be indistinguishable from evidence six months from now unless it's rejected at the door.

## 2. Every framework change requires evidence.

Before editing a rule in this repository, the change must be traceable to a specific, dated, numbered result — not a general impression of how the account has been performing. If the evidence can't be pointed to, the change does not get made, no matter how confident the reasoning behind it sounds.

## 3. Accepted evidence sources:

- **Historical account data** — documented in [`docs/historical-analysis.md`](historical-analysis.md)
- **Controlled experiments** — logged in [`docs/experiments.md`](experiments.md)
- **Winning campaigns** — logged in [`docs/winners.md`](winners.md)
- **Winning creatives** — the creative-level detail inside a [`docs/winners.md`](winners.md) entry or [`docs/historical-analysis.md`](historical-analysis.md)
- **Verified Shopify data** — live pulls from canton-eg.com's product catalog, orders, or store settings, as documented in [`docs/landing-page-framework.md`](landing-page-framework.md) and [`docs/historical-analysis.md`](historical-analysis.md)

Documented failures (see [`docs/failures.md`](failures.md)) are evidence too — a failure that's been logged with its hypothesis, execution, and failure reason is exactly as valid a basis for a rule change as a winner is. What's not evidence is a failure nobody wrote down.

## 4. Meta documentation alone is NOT evidence.

Meta's official ad platform documentation, help center articles, or blueprint courses describe how the platform is *designed* to work in general. They are not evidence of how it *actually* performs for Canton's specific products, audience, and market. A claim like "Meta recommends X" is not a valid citation anywhere in this repository unless X has also been independently confirmed against Canton's own account data.

## 5. YouTube videos are NOT evidence.

Marketing YouTube content, course material, "how I scaled to $X" videos, and similar third-party media are not evidence, regardless of the creator's credentials or view count. They may be a source of *hypotheses* to test — a hypothesis is allowed to originate anywhere — but a hypothesis only becomes framework material after it's been run as a logged experiment in [`docs/experiments.md`](experiments.md) against Canton's own account.

## 6. Community opinions are NOT evidence.

Forum threads, Slack groups, agency chatter, "everyone knows," and similar community consensus are not evidence. The same rule as above applies: these are acceptable as a source of ideas to test, never as a basis to change a rule directly.

## 7. Every strategic change must reference: Historical Analysis, Experiments, or Winners.

Any edit to a framework document that changes a rule, a benchmark, a threshold, or a recommended structure must cite which of the three evidence files justifies it:

- [`docs/historical-analysis.md`](historical-analysis.md), or
- [`docs/experiments.md`](experiments.md), or
- [`docs/winners.md`](winners.md)

(and, per Rule 3, a logged entry in [`docs/failures.md`](failures.md) also satisfies this requirement.) A pull request, commit, or edit that changes a rule without this citation should be treated as incomplete, not as a legitimate framework update — see [`CHANGELOG.md`](../CHANGELOG.md) for how changes are recorded once they meet this bar.

## 8. Historical replication must always precede optimization.

Before changing a winning framework, it must first be reproduced successfully. A historical pattern — even one classified Confirmed at 100% confidence — is not licensed for further optimization, scaling, or variation until it has been rebuilt from scratch under current conditions and shown to still work. This is why [`docs/experiments-roadmap.md`](experiments-roadmap.md) opens with EXP-003, a pure replication test with zero variables changed, before any of the isolated-variable experiments that follow it. Skipping straight to "improve the winner" without first confirming the winner still reproduces is exactly the kind of confident-sounding shortcut Rule 1 exists to block — replication is not busywork, it is the evidence that the historical finding still holds.

## 9. Pre-launch execution corrections are not experimental changes.

An experiment's data collection begins at first delivery — the first impression, click, or spend against it — not at the moment its objects (campaign/ad set/ads) are created in Ads Manager. If an execution defect (an ad built the wrong way, a wrong targeting value, a missing setting) is found and fixed **before any delivery has occurred**, that correction restores the experiment to its originally approved design; it does not create a new experiment, does not require a new experiment ID, and does not need to be logged as a variable change. Only a change made **after delivery has begun** counts as an experimental modification requiring a new entry or a new experiment ID. This distinction was established on 2026-08-02 for EXP-003 ([`docs/experiments.md`](experiments.md)), where four ads were found using Media-Library-built creative instead of the required Existing Posts during the final pre-launch audit, corrected before the campaign had generated any impressions, clicks, spend, or purchases, and logged as a Pre-launch Execution Correction rather than a new experiment.

---

## How this applies day to day

- Reading [`docs/decision-tree.md`](decision-tree.md) to diagnose a live problem is not a "framework change" and doesn't require new evidence — it's using the existing evidence.
- Proposing a *new* rule (e.g., a new CTR floor, a new placement default, a new audience strategy) *is* a framework change and needs a citation under Rule 7 before it gets written into [`docs/framework.md`](framework.md), [`docs/campaign-structure.md`](campaign-structure.md), [`docs/creative-framework.md`](creative-framework.md), or [`docs/landing-page-framework.md`](landing-page-framework.md).
- When in doubt whether something counts as evidence, ask: "could I point to a specific ad set, a specific date, and a specific number?" If not, it's an opinion, however reasonable it sounds.


---

**See also:** [`docs/repository-rules.md`](repository-rules.md) — the operating constitution these evidence rules sit under; [`docs/kpi-thresholds.md`](kpi-thresholds.md) for where evidence-backed benchmark values are recorded once they exist; [`docs/hypotheses.md`](hypotheses.md) for open hypotheses awaiting the evidence Rule 8 requires; [`docs/experiments-roadmap.md`](experiments-roadmap.md) for the prioritized queue that resolves them, replication-first.
