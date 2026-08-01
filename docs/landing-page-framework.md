# Landing Page Framework

Everything in this file is pulled directly from Canton's live Shopify store (canton-eg.com, Basic plan, EGP currency) — product data, tags, descriptions, and the store's own draft-product testing pattern. Nothing here is generic Shopify or CRO advice.

## Winning structure (as currently built by Canton)

Every recently-updated Canton product description follows the same fixed sequence:

1. **Bundle offer, stated as a number, first line.** E.g. "🎁 اشتري 2 واحصلي على الثالثة مجانًا — يتطبق تلقائيًا عند الدفع" (buy 2, get the 3rd free — applies automatically at checkout). This mirrors exactly what ولاد's winning ad copy led with — the ad and the landing page are copy-consistent, which is itself the point (message match).
2. **Trust/logistics line, repeated verbatim across products:** "🚚 شحن سريع لكل المحافظات | 💵 دفع عند الاستلام | 🔄 استبدال واسترجاع وفق الشروط والأحكام" (fast shipping to all governorates | cash on delivery | exchange & return per terms). This exact line appears on multiple unrelated products (tunic, Boho set, Benetton dress) — it's a standardized trust block, not written per-product.
3. **Price anchor shown as a discount chain**: e.g. "وفري 300 جنيه دلوقتي 799 جنيه 499 جنيه" (save EGP300, was EGP799, now EGP499) — strike-through original price next to the sale price, framed as savings first.
4. **Product feature bullets** — short, benefit-first, not spec-first (e.g. "مش هيحرّه ويعرّقه بالنهار" — won't overheat/sweat him during the day — a use-case benefit, not a fabric spec).

## Trust

- The COD (دفع عند الاستلام) line is present on every product reviewed — this is Canton's primary payment trust mechanism, consistent with an Egyptian e-commerce market where COD is the default expectation, not an add-on.
- The exchange/return line ("استبدال واسترجاع وفق الشروط والأحكام") is boilerplate, not specific — it references "terms and conditions" without stating them inline. **Open question, not yet resolved with evidence:** whether a more specific, visible return policy (days, process) would reduce the checkout-abandonment problem documented in `historical-analysis.md` (ولاد: only 22.1% of Initiated Checkouts became Purchases). This is the single highest-leverage unknown in Canton's funnel and should be tested directly rather than assumed.

## FAQ

NOT PRESENT in the product data reviewed. No FAQ section or dedicated FAQ block was found on any product pulled from the catalog. This is a gap, not a documented practice — flag any campaign relying on FAQ-driven trust-building as unverified until FAQ content actually exists on the page.

## CTA

Explicit CTA button copy was NOT captured in this pull (Shopify's product API returns description/tags/pricing, not theme-level button text). Do not assume a specific CTA wording is "proven" — this needs a direct page inspection before any claim is made about it.

## Reviews

NOT PRESENT in the product data reviewed — no review count, rating, or testimonial content appeared in any pulled product's description or tags. If reviews exist elsewhere in the theme (a reviews app widget, for instance), they are not part of the product's own data and were not verified here. Given the checkout-completion gap documented in `historical-analysis.md`, adding visible social proof at or near the checkout/ATC decision point is a reasonable framework hypothesis — but it is a hypothesis, not evidence, until tested.

## Scarcity

Time-bound scarcity is present but tied to real calendar events, not artificial countdowns: ولاد's copy used "لحد آخر رمضان فقط" (until the last day of Ramadan only) — a real, credible deadline tied to a real seasonal window, not a generic "limited time" claim. **Rule: scarcity framing should anchor to a real, verifiable event (season end, stock level, collection changeover) — Canton has no evidence to support fabricated urgency, and using a real deadline is what the one documented winner actually did.**

## Guarantees

No explicit money-back or satisfaction guarantee language was found beyond the standard exchange/return line. This is a gap relative to common e-commerce trust patterns, but Canton has no internal evidence yet on whether adding one would move conversion — record as untested, not as a recommendation to copy from outside best practice.

## Sizing (Canton's actual, repeated pattern)

This is the single most consistent structural element found across the whole catalog and it matches the ولاد ad copy exactly:

- **One-size, weight-based sizing** is used repeatedly for kids' and unisex products: "بنطلون وايد ليج – One Size" (Wide Leg pants, one size), described by weight range rather than a size chart.
- **Two-band extended sizing** for adult women's items: e.g. the Wide Leg pants product splits into `M-L` and `XL-2XL` bands rather than a full numeric size run — reduces variant complexity while still covering a wider range.
- SKU-level sizing is embedded directly in the SKU string (`CTN-KD-0030-08` = size 8), and variant titles pair size with color (`اسود / 7-8`), which keeps size and color selection as a single dropdown decision rather than two separate ones.

**Rule: any new kids' or unisex product listing should default to weight/age-based one-size sizing unless there's a specific reason to run full numeric sizing — this is Canton's dominant, repeated pattern, and it's the exact framing that appeared on the account's best-documented ROAS winner.**

## Mobile

Not directly measurable from the Shopify product data pulled here, but the Meta-side evidence is unambiguous: on ولاด, **100% of purchases (62/62) came through the Facebook/Instagram native mobile app**, with desktop and mobile-web driving zero purchases despite some spend and even higher CTRs on trivial samples. **Rule: every landing page decision must be mobile-app-webview-first.** Desktop layout, desktop-only interactions, or anything that assumes a full mobile browser (vs. an in-app webview) should be deprioritized — Canton's actual buyers are arriving through the Meta in-app browser on a phone, not a desktop or even a standalone mobile browser.

## Landing page testing method (Canton's real, observed workflow)

Canton's Shopify catalog contains a direct, reusable A/B testing pattern already in use: **duplicate the live product as a separate DRAFT product prefixed `[LP TEST]`**, e.g. `[LP TEST] تونيك أوفر سايز – كولكشن جديد` sitting alongside the live `تونيك أوفر سايز – كولكشن جديد`. Both were created/updated on the same day (2026-08-01), same price, same tags, same bundle offer — the draft copy exists to test new copy/layout/imagery without touching the live, ad-linked product URL.

**Rule: use this exact pattern for landing page testing going forward.**
1. Duplicate the live product.
2. Prefix the duplicate's title with `[LP TEST]` and set status to `DRAFT`.
3. Make the variant/copy/layout changes on the draft.
4. Test the draft via a direct preview link (not live ad traffic) or promote it to `ACTIVE` under a separate handle if a real split test against live traffic is needed.
5. Once a version wins, apply the winning changes to the live product directly — don't leave two parallel live listings for the same product, which would split reviews, inventory tracking, and ad attribution.

This is a real, evidenced-based workflow already present in the store, not an invented recommendation — three `[LP TEST]` draft duplicates existed in the catalog at the time of this audit (Tunic, Boho set, Benetton dress), all created the same day, confirming this is an active, repeatable practice, not a one-off.
