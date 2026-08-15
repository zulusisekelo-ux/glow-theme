# GLOW backlog

Priority order. Tick as done, add findings underneath rather than deleting.
Last worked: 2026-08-15.

## Blocking — before any ad spend

- [ ] **Gel.** Source whitening gel and confirm it ships inside every kit. The product page says "Whitening gel, included free (R149 value)". If gel is not in the box, that line must come down the same day. Supplier image `description-4.jpg` reads "(Not including gel)". Cost impact ~R40/unit: gross R480.68 → ~R440.
- [x] Remove fabricated testimonials from the homepage. — replaced with "No reviews yet. So here is our promise instead."
- [x] Remove the About-page line about verified reviews. — About page rewritten; the ASA-risky phrase "clinically-tested" also removed.
- [x] Deactivate the **Test payment gateway**. — gone; **Yoco is Active**.

## Store

- [x] Install **Search & Discovery** and set complementary products.
      Kit → Desensitising Gel, V34 Colour Corrector, Whitening Gel 3-Syringes.
      Verified live: `/recommendations/products?intent=complementary&product_id=10387424837915`
      returns all three under the heading "Complete your kit".
- [x] Replace the three placeholder add-on images with real product photos. — real Temu
      photography injected at full resolution; all three products have a live image.
- [x] **Cart-drawer upsell** — deployed 2026-08-15 (commit f00a9dd). Shows up to 2 add-ons not
      already in cart above the footer. Adds via `/cart/add` with full re-render.
      Live in `snippets/cart-drawer.liquid`.
- [ ] **Replace Desensitising Gel (19% margin, 3 lifetime sales) with LED Mouth Tray 2-Pack.**
      - Reason: direct accessory to kit, users need replacements, 70%+ margin
      - Cost: R35–R45/unit (Alibaba bulk, MOQ ~50–100)
      - Price: R149
      - Gross: R104–R114 (best on store after V34)
      - Sourcing: Alibaba "LED teeth whitening tray replacement" or Dental Lab Shop (R0.71/tray, MOQ 30)
      - Images: silicone trays front/side profile, in packaging, generic stock OK
      - Timeline: source sample → approve → order 100 units → product page live (5–7 days)
- [ ] Add a Contact page (`/pages/contact` currently 404s). Trust signal and a Meta
      commerce-policy expectation. Use the `page.contact` template.
- [ ] Confirm free delivery applies to add-ons bought alone (shipping profile check in admin).
- [ ] Consider a 2-device bundle at R999 to lift AOV.
- [ ] Add-ons have only 1 image each. Two more per product would help conversion.

### Margin watch
| Product | Cost | Sells | Gross | Note |
|---|---|---|---|---|
| Kit | ~R168 | R649 | R480.68 | drops to ~R440 if gel is packed |
| Whitening Gel — 3 Syringes | R82 | R149 | R67 | 11K+ sold at source |
| V34 Colour Corrector | R52 | R159 | R107 | best attach margin — show first |
| LED Mouth Tray 2-Pack | R40 | R149 | R109 | replaces Desensitising Gel; direct accessory |

## Domain

- [ ] `glow.co.za` is **taken**. `glowsa.co.za` parked for resale.
- [ ] Available: `glowteeth.co.za`, `glowwhitening.co.za`, `getglow.co.za`, `glowsmile.co.za`, `tryglow.co.za`, `glowkit.co.za`.
- [ ] Cheapest 3-year domain-only: Truehost ZA ~R227. Flat-priced, lower renewal risk: Register Domain SA / Absolute Hosting ~R285.
- [ ] Shopify DNS: A → `23.227.38.65`, CNAME `www` → `shops.myshopify.com`.

## Payments

- [x] Yoco installed and **Active**.
- [ ] Resolve PayPal "Setup incomplete" (or remove it — a half-set-up gateway at checkout costs sales).

## Meta — owner actions, out of scope for the agent

- [ ] Add payment method to the ad account (owner only).
- [ ] Create the Facebook Page, link Instagram.
- [ ] Install the Meta app in Shopify, connect the pixel.
- [ ] **Verify the pixel fires** — ViewContent, AddToCart, InitiateCheckout. Observed, not assumed.

## Creative — ready, not yet used

12 static ad files, 6 self-filmable UGC scripts, copy bank and campaign structure are in project doc `claude/20`. Compliance ruleset is in `CLAUDE.md`.

- [ ] Film Scripts 1 and 2. Script 2 needs no face and no voice — hands-only unboxing, ~12 seconds.
- [ ] Real review screenshots for the product and add-ons.

## Regulatory

- [ ] Confirm the SA position for a peroxide cosmetic whitening product under the
      Foodstuffs, Cosmetics and Disinfectants Act 54 of 1972 before running claims-based ads.
      Research blocked 2026-08-15 by a tool limit; retry. Starting points:
      SAHPRA's copy of the Act, and the CMS beauty-regulation guide for South Africa.
