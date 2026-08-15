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
- [ ] Add a Contact page (`/pages/contact` currently 404s). Trust signal and a Meta
      commerce-policy expectation. Use the `page.contact` template.
- [ ] Confirm free delivery applies to add-ons bought alone (shipping profile check in admin).
- [ ] Consider a 2-device bundle at R999 to lift AOV.
- [ ] Add-ons have only 1 image each. Two more per product would help conversion.
- [ ] Optional, deprioritised: three further add-ons from `claude/16` (whitening pen R149,
      niacinamide toothpaste R139, mouth tray 2-pack R130). More SKUs = more supplier
      surface area for no launch benefit. Revisit after the first profitable week.

### Margin watch
| Product | Cost | Sells | Gross | Note |
|---|---|---|---|---|
| Kit | ~R168 | R649 | R480.68 | drops to ~R440 if gel is packed |
| Whitening Gel — 3 Syringes | R82 | R149 | R67 | 11K+ sold at source |
| V34 Colour Corrector | R52 | R159 | R107 | best attach margin — show first |
| Desensitising Gel | R113 | R139 | **R26** | 19% — only 3 sold at source. Reprice to R179 or drop. User said keep as is. |

## Domain

- [ ] `glow.co.za` is **taken**. `glowsa.co.za` parked for resale.
- [ ] Available: `glowteeth.co.za`, `glowwhitening.co.za`, `getglow.co.za`, `glowsmile.co.za`, `tryglow.co.za`, `glowkit.co.za`.
- [ ] Cheapest 3-year domain-only: Truehost ZA ~R227. Flat-price, lower risk: Register Domain SA / Absolute Hosting ~R285.
- [ ] Shopify DNS: A → `23.227.38.65`, CNAME `www` → `shops.myshopify.com`.

## Payments

- [x] Yoco installed and **Active**.
- [ ] Resolve PayPal "Setup incomplete" (or remove it — a half-set-up gateway at checkout costs sales).

## Meta — owner actions, out of scope for the agent

- [ ] Add payment method to the ad account (owner only).
- [ ] Create the Facebook Page, link Instagram.
- [ ] Install the Meta app in Shopify, connect the pixel.
- [ ] **Verify the pixel fires** — ViewContent, AddToCart, InitiateCheckout. Observed, not assumed.

## Regulatory

- [ ] Confirm the SA position for a peroxide cosmetic whitening product under the
      Foodstuffs, Cosmetics and Disinfectants Act 54 of 1972 before running claims-based ads.
      Research blocked 2026-08-15 by a tool limit; retry. Starting points:
      SAHPRA's copy of the Act, and the CMS beauty-regulation guide for South Africa.
