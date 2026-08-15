# GLOW backlog

Priority order. Tick as done, add findings underneath rather than deleting.
**Last worked: 15 Aug 2026.**

## Blocking — before any ad spend

- [ ] **Gel. THE ONE REMAINING BLOCKER.** The product page says "Whitening gel, included free (R149 value)". That is only true if gel is physically packed in every kit. Supplier image `description-4.jpg` reads "(Not including gel)". Source gel and include it, or take the line down the same day. Cost ~R40/unit, gross profit R480.68 → ~R440.
- [x] ~~Remove fabricated testimonials from the homepage.~~ Done 15 Aug. Three invented reviews (Thandi/Cape Town, Johan/Johannesburg, Lindiwe/Durban) removed, replaced with an honest "No reviews yet, so here is our promise instead" section.
- [x] ~~Remove the About-page line about verified purchases.~~ Done 15 Aug. The whole About page was rewritten — it contained **"clinically-tested"**, the exact phrase HiSmile was banned for, plus "same professional-grade whitening formula used in dental offices" and "save over 80% versus the dentist".
- [x] ~~Deactivate the Test payment gateway.~~ Gone as of 15 Aug. **Yoco is now Active.**
- [x] ~~Fix "10 minutes" vs 30 minutes on the product page.~~ Done 15 Aug.
- [x] ~~Eight unsupportable claim tiles on the homepage.~~ Done 15 Aug — found while removing testimonials. Included "Most see visible whitening within one session", "The same whitening strength used in dental offices", "Professional formula that will not damage your teeth", "The same peroxide concentration dental offices use". All rewritten to factual statements.

## Store

- [ ] Install **Search & Discovery** (free, Shopify first-party) and set complementary products: kit → gel refills + desensitising gel; cart drawer → V34 corrector. **Highest-value remaining store task** — the three add-ons currently exist but nothing offers them at the point of decision.
- [ ] Add three further add-ons from `claude/16`: whitening pen R149, niacinamide brightening toothpaste R139, extra mouth tray 2-pack R130.
- [ ] Replace the three placeholder add-on images with real product photos once sourced from Temu.
- [ ] Confirm free delivery applies to add-ons bought alone.
- [ ] Consider a 2-device bundle at R999 to lift AOV.

## Domain

- [ ] Register one. `glow.co.za` is **taken** (active glow-stick retailer). `glowsa.co.za` is parked for resale.
- [ ] Confirmed available: **glowteeth.co.za**, **glowwhitening.co.za**, getglow.co.za, glowsmile.co.za, tryglow.co.za, glowkit.co.za.
- [ ] Cheapest 3-year domain-only: Truehost ZA ~R227. Flat-priced, lower renewal risk: Register Domain SA / Absolute Hosting ~R285.
- [ ] Shopify DNS: A record → `23.227.38.65`, CNAME `www` → `shops.myshopify.com`.

## Payments

- [x] ~~Install and activate Yoco.~~ Active as of 15 Aug.
- [ ] Resolve PayPal — still shows "Activate PayPal".

## Meta

Business portfolio **GLOW Whitening SA** exists, `business_id=1087447840804837`. Ad account created with **ZAR / GMT+2** (the currency default was USD and would have been permanent).

- [ ] Add payment method to the ad account (owner only — never automate this).
- [ ] Create the Facebook Page, link Instagram.
- [ ] Install the Meta app in Shopify, connect the pixel.
- [ ] **Verify the pixel fires** — ViewContent, AddToCart, InitiateCheckout. Observed, not assumed.

## Creative — ready, not yet used

12 static ad files, 6 self-filmable UGC scripts, copy bank and campaign structure are in project doc `claude/20`. Compliance ruleset is in `CLAUDE.md`.

- [ ] Film Scripts 1 and 2. Script 2 needs no face and no voice — hands-only unboxing, ~12 seconds.
- [ ] Real review screenshots for the product and add-ons.

## Regulatory

- [ ] Confirm the SA position for a peroxide cosmetic whitening product under the Foodstuffs, Cosmetics and Disinfectants Act before running claims-based ads.
