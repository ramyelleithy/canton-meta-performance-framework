# Meta Ads Decision Tree

This is the diagnostic path for any underperforming ad set. Walk it top to bottom, stage by stage — do not skip to a conclusion (e.g. "the audience is wrong") before ruling out the stages above it. Each branch below is grounded in a specific funnel stage Canton actually tracks: Impressions → CTR → Clicks → LPV → ViewContent → ATC → IC → Purchase.

```
                        ┌─────────────────────┐
                        │   Spend is flowing   │
                        └──────────┬───────────┘
                                   │
                    ┌──────────────┴──────────────┐
                    │      Is CTR low?             │
                    │   (Canton 1 healthy range:    │
                    │    7–10% on winning ad sets)  │
                    └──────────────┬──────────────┘
                     YES ↓                    ↓ NO
        ┌────────────────────────┐   ┌───────────────────────┐
        │   → CREATIVE PROBLEM    │   │  Is LPV low relative   │
        │                         │   │  to clicks?            │
        │  Check:                │   │  (healthy: LPV should  │
        │  - Hook (first line/    │   │  track close to clicks;│
        │    first frame)         │   │  ولاد ran ~18% LPV/    │
        │  - Thumbnail/first      │   │  click on its best day)│
        │    frame is not the     │   └──────────┬─────────────┘
        │    product itself       │     YES ↓              ↓ NO
        │  - Offer not stated     │  ┌──────────────┐ ┌──────────────┐
        │    early enough         │  │ → LANDING     │ │ Is ATC low   │
        │  - Creative fatigue     │  │   PAGE PROBLEM │ │ relative to  │
        │    (check frequency —   │  │                │ │ VC?          │
        │    ولاد never exceeded  │  │ Check:         │ └──────┬───────┘
        │    1.55 freq lifetime;  │  │ - Page load     │  YES↓      ↓NO
        │    rising freq with     │  │   speed on      │ ┌────────┐ ┌──────────┐
        │    falling CTR = fatigue│  │   mobile        │ │→ OFFER  │ │ Is IC low │
        │  - Wrong placement mix  │  │ - Ad promise    │ │  PROBLEM│ │ relative  │
        │    (feed converted 24.7x│  │   matches page   │ │         │ │ to ATC?   │
        │    ROAS for ولاد vs.    │  │   headline       │ │Check:   │ │(note:     │
        │    9.9x on Reels —      │  │ - Broken/slow     │ │- Price   │ │ولاد's IC  │
        │    check where budget    │  │   redirect       │ │  anchor  │ │exceeded   │
        │    is actually landing)  │  │ - Not mobile-     │ │  visible │ │ATC 4.4x — │
        └─────────────────────────┘  │   optimized       │ │  (strike-│ │if ATC is  │
                                       └───────────────────┘ │  through │ │your only  │
                                                              │  pricing)│ │cart signal│
                                                              │- Bundle  │ │it may be  │
                                                              │  mechanic│ │undercount-│
                                                              │  unclear │ │ing — trust│
                                                              │- Sizing  │ │IC instead)│
                                                              │  logic   │ └─────┬─────┘
                                                              │  confusing│  YES↓    ↓NO
                                                              └──────────┘ ┌────────┐┌──────────┐
                                                                            │→CHECKOUT││Is Purchase│
                                                                            │ PROBLEM ││low rel.   │
                                                                            │         ││to IC?     │
                                                                            │Check:   ││(ولاد: only│
                                                                            │- Form    ││22.1% of IC│
                                                                            │  length  ││→Purchase —│
                                                                            │- COD     ││this is the│
                                                                            │  confirm ││single     │
                                                                            │  flow    ││biggest    │
                                                                            │  friction││leak Canton│
                                                                            │- Payment ││has evidence│
                                                                            │  method   ││for)       │
                                                                            │  options  │└─────┬─────┘
                                                                            └──────────┘   YES↓
                                                                                    ┌───────────────────┐
                                                                                    │→ TRUST / PRODUCT /  │
                                                                                    │  MARKET PROBLEM      │
                                                                                    │                       │
                                                                                    │ Check:                │
                                                                                    │ - Reviews/social proof │
                                                                                    │   present at checkout  │
                                                                                    │ - Guarantee/return      │
                                                                                    │   policy visible        │
                                                                                    │   (Canton's standard    │
                                                                                    │   line: "استبدال       │
                                                                                    │   واسترجاع وفق الشروط  │
                                                                                    │   والأحكام" — is it     │
                                                                                    │   actually reassuring   │
                                                                                    │   or just boilerplate?) │
                                                                                    │ - Price vs. perceived    │
                                                                                    │   value at this exact    │
                                                                                    │   moment (Ramadan/season │
                                                                                    │   framing, as ولاد used) │
                                                                                    │ - COD no-show risk —     │
                                                                                    │   this is a demand-      │
                                                                                    │   confirmation problem,  │
                                                                                    │   not an ad problem      │
                                                                                    └───────────────────────────┘
```

## The rule in plain text

1. **CTR low → Creative.** Nothing downstream matters until people stop and click. Compare against Canton 1's real range: winning ad sets ran 7–10% CTR; if you're materially below that, the creative — not the audience — is the first suspect.
2. **CTR fine, LPV low → Landing Page.** People are clicking but not reaching (or the pixel isn't registering they reached) the page. Check load speed and message match first.
3. **LPV fine, ATC low → Offer.** They landed and looked, but the offer isn't compelling enough to add to cart. Check price anchoring, bundle clarity, and sizing logic — Canton's own products lean heavily on weight/age-based one-size sizing and Buy-X-Get-Y bundles; if those aren't crystal clear on the page, ATC suffers.
4. **ATC fine, IC low → Checkout friction.** Note: on Canton's own pixel setup, IC has historically fired *more* than ATC (ولاد: 280 IC vs. 63 ATC), which suggests many Canton checkout flows skip a discrete Add-to-Cart step entirely (a direct "Order Now" button). If that's the case for the flow you're auditing, treat IC — not ATC — as the real mid-funnel signal, and don't over-index on a low ATC number that may just be a tracking artifact.
5. **IC fine, Purchase low → Checkout completion / trust / product / market.** This is the stage with the strongest documented evidence of being Canton's actual weak point: on ولاد, only 22.1% of Initiated Checkouts became Purchases — meaning ~78% of people who started checkout dropped before completing. That gap is not a Meta problem or a targeting problem; it lives in the checkout form, COD confirmation flow, trust signals, and possibly order-confirmation follow-up (phone confirmation calls, WhatsApp confirmation, etc. — outside Meta's control entirely).

## Anti-pattern to avoid

Do not diagnose "audience is wrong" as a first move. None of Canton's documented winners used narrow interest/behavior targeting — ولاد ran on fully broad Advantage+ targeting (age 21–65, no interests, no lookalikes, Advantage Audience on) and still converged tightly on a specific buyer (Female, 35–44, Cairo/Giza, night hours) purely through delivery optimization. If a broad ad set isn't converging the way ولاد did, the more likely culprits are creative and offer clarity, not "we need better targeting."
