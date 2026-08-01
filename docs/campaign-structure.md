# Campaign Structure

## Naming convention (current — Canton 3)

Canton 3's live campaign is named:

```
Canton | Tunic | ABO | Purchase | EG | V1
```

with a duplicate ad set tested as:

```
Canton | Tunic | ABO | Purchase | EG | V1 - Copy
```

This decodes to a fixed field order:

```
{Brand} | {Product/Category} | {ABO or CBO} | {Objective} | {Country} | {Version}
```

**This is the mandatory naming convention going forward.** Every new campaign must follow this exact field order. Fields:

| Field | Values used so far | Notes |
|---|---|---|
| Brand | `Canton` | Always Canton — this account only runs Canton |
| Product/Category | `Tunic` (seen); should generalize to product names matching Shopify `productType`/handle (e.g. `Pants`, `Kids Set`, `Dress`) | Keep it short — this is a label, not a description |
| Structure | `ABO` (seen) or `CBO` | See ABO vs CBO rules below |
| Objective | `Purchase` (seen) | Matches the Meta optimization goal in plain language |
| Country | `EG` | Egypt-only account as of this writing |
| Version | `V1`, and duplicates suffixed `- Copy` | Increment on real structural changes (new targeting/creative set), not on every minor edit |

## Historical contrast — why this matters

Canton 1's ad sets did **not** follow any consistent naming convention. Real examples pulled from the account: `ولاد`, `حريمي 1`, `US Polo | Winter | Old`, `AS|TS|Broad|Purchase`, `New Sales Ad Set`, `New Sales Ad Set (بنطلون)`, `New Sales Ad Set - Apr 2026`, `New Sales Ad Set - Copy (LC Wideleg)`. Some names describe the product (`ولاد`, `حريمي 1`), some describe a targeting strategy (`AS|TS|Broad|Purchase` — likely "Advantage Shopping | Targeted Shopping | Broad"), some are just generic labels with no encoded information at all (`New Sales Ad Set`). This made it impossible to tell, from the name alone, what structure or strategy a given ad set used — every audit required opening the ad set itself. Canton 3's structured naming convention directly fixes this. **Do not regress to Canton 1's naming style.**

## ABO vs CBO

**Canton 3's current default is ABO** (Ad Set Budget Optimization) — the live Tunic campaign runs two separate ad sets, each carrying its own budget (EGP300/day each), rather than one shared campaign budget.

**Canton 1's "Pants" campaign (home of the ولاד winner) ran CBO** — a single campaign-level daily budget of EGP250.00 shared across its ad sets, with Meta's auction deciding allocation. This is a documented fact, not a recommendation either way: ولاد's own spend curve (EGP415→574→386 across Mar 4–6, tracking its rising ROAS) was Meta's CBO auction reallocating budget toward it automatically — Canton never manually adjusted its budget.

**Framework decision, not yet backed by a controlled comparison:** use ABO during Discovery (so each test gets a guaranteed minimum spend and isn't starved by a sibling ad set — this is exactly what happened to ولاد's own video-creative ad, which got only EGP7.11 of a EGP2,111.90 total spend because the photo ad converted first and captured the CBO auction). Move to CBO once multiple ad sets in a campaign have each independently cleared Validation, so the auction can allocate budget toward whichever is currently most efficient. This is a working rule, not proven history — Canton has not yet run a documented head-to-head of ABO vs. CBO for the same product/audience.

## Campaign hierarchy

```
Account (Canton 1 / Canton 2 / Canton 3)
 └─ Campaign  — {Brand} | {Product} | {ABO/CBO} | {Objective} | {Country} | {Version}
     └─ Ad Set — named for the audience/segment being tested (see below)
         └─ Ad — named for the creative format/variant (e.g. "فيديو", "صور")
```

**Ad set naming:** Canton 1's ad-set names that carried real information were segment-descriptive: `ولاد` (boys), `حريمي 1` (women's #1), `Men & Women Broad`. Follow that pattern — the ad set name should say *who* it targets or what test it represents, not repeat the campaign name.

**Ad naming:** Canton 1 named ads by creative format — `فيديو` (video), `صور` (photos) — which is minimal but functional; it tells you at a glance which creative type is which without opening the ad. Continue this, but extend it with a short content tag once more than one creative per format exists per ad set, e.g. `صور - v2 - offer-hook`, to avoid the ambiguity Canton 1 had (two ads named generically by format only, with no way to tell what copy/angle each used without opening the creative).

## Products and creative organization

Shopify's actual SKU/tag taxonomy should drive campaign-to-product mapping directly:

- SKU prefixes observed: `CTN-WM-####` (women), `CTN-KD-####` (kids), `CTN-UN-####` (unisex)
- Offer tags observed: `bundle:2-pieces`, `bundle:3-pieces`, `offer-bxgy`, `Buy2 Get1`, `hot-deals`
- Product-type tags observed: `Tunic`, `Kids`, `Women`, `Long Sleeve`, `Oversized`, `New Collection`, `summer`, `girls`, `boys`, `dresses`, `sets`

**Rule:** a campaign's Product/Category field should map 1:1 to a Shopify `productType` or a clearly scoped SKU family, not a loose grouping. This keeps reporting (Meta side) traceable back to inventory and margin (Shopify side) without manual reconciliation.

## Versions and lifecycle

- `V1` is the first structural version of a campaign. A new version number is warranted when the **audience, objective, or budget structure (ABO/CBO)** changes — not for routine creative refreshes, which live inside the ad set as new ads.
- A `- Copy` suffix (as seen on Canton 3's Tunic campaign) is the correct mechanism for running a controlled duplicate test — same structure, isolated as its own ad set so its performance can be measured independently rather than blended into the original.
- Campaign lifecycle should mirror the four stages in `docs/framework.md` (Discovery → Validation → Scaling → Prime). A campaign's status (ACTIVE/PAUSED) and its lifecycle stage are two different things — ولاد's own campaign ("Pants") shows `effective_status: PAUSED` today, but during Mar 2–7 it was clearly in Validation/early Scaling by performance, regardless of what its status flag says months later. Track lifecycle stage explicitly; don't infer it from status alone.
