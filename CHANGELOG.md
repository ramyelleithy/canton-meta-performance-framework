# Changelog

All notable changes to the Canton Meta Performance Framework are recorded here. This file tracks the evolution of the framework itself — not day-to-day ad account activity, which belongs in `docs/historical-analysis.md`.

Per operating rule: **from v1.0 onward, any change to this framework must be justified by new data (a new audit, a new ad set result, a new Shopify pattern), not by opinion or intuition.** Every changelog entry should be traceable to evidence recorded in `docs/historical-analysis.md`.

## v1.0 — Initial release

**Summary:**
- Initial Meta Ads Operating System established as the single source of truth for Canton Store Meta Ads decisions.
- Historical Canton 1 analysis — full forensic audit of the account's proven winner (ولاد, campaign "Pants," ROAS 23.48x), account-wide top-10 ad set ranking, and Canton 3's current live Discovery-stage state.
- Decision Tree — CTR → LPV → ATC → IC → Purchase diagnostic path, grounded in ولاد's actual funnel numbers.
- Campaign Framework — the Discovery → Validation → Scaling → Prime lifecycle, and the naming/ABO-CBO structure rules.
- Creative Framework — buyer-vs-wearer copy principle, bundle-first hook requirement, and the image-vs-video delivery-starvation finding.
- Landing Page Framework — Canton's real Shopify offer, trust, and sizing patterns, plus the `[LP TEST]` draft-duplicate testing workflow already in use in the store.
- Audit Checklist — full pre-launch and in-flight checklist across campaign, ad set, ads, landing, creative, tracking/pixel, offer, and Shopify.
- Playbook — step-by-step SOPs for launching a Discovery test, promoting to Validation, scaling a winner, running a weekly audit, killing/rebuilding a loser, and testing a landing page.

**Repository consolidated:** this repository (`ramyelleithy/canton-meta-performance-framework`) is the single source of truth. A duplicate copy that had been temporarily placed inside `ramyelleithy/canton-store` was removed to prevent drift between two versions.

**Known open questions carried into v1.0** (see `docs/historical-analysis.md` → "Failures & Open Questions"):
- CBO manual budget scaling has never been tested on a Canton ad set — ولاد's own scaling was 100% algorithmic.
- Video creative has never been fairly tested against photo creative — the one documented case starved the video ad of delivery.
- The root cause of ولاد's 15-day dark period (Mar 8–22) is undocumented — activity-log access was unavailable at time of audit.
- The checkout-completion gap (78% of Initiated Checkouts never became Purchases) has no root-cause diagnostic data yet — this is the framework's top investigation priority.
- No comments/engagement sentiment data has ever been pulled for any Canton ad set.

---

## How to add a new entry

1. Confirm the change is backed by new evidence — a live account pull, a new forensic audit, a new Shopify catalog observation. If it isn't, it doesn't belong here or in the framework docs.
2. Update the relevant `docs/*.md` file(s) directly, adding the new evidence and, if warranted, a new or revised rule.
3. Add the corresponding evidence entry to `docs/historical-analysis.md` so the claim is traceable.
4. Add a new version section here (e.g. `## v1.1`) summarizing what changed and which file(s) were touched, and why (cite the evidence).
