# GLOW backlog

Priority order. Tick as done, add findings underneath rather than deleting.
Last worked: 2026-08-15 (late).

## CORRECTION — read this first

An earlier commit today ("Mark gel blocker done — owner confirms gel is packaged")
is **wrong** and has been reverted in substance. The owner has since confirmed the
opposite: **the gel is NOT packed inside the device box.** A free gel pack is
shipped alongside the kit with every order.

All storefront copy has been rewritten to say exactly that. Do not "correct" it back.

Live wording now in use:
- Product page, under "What you get":
  "Free whitening gel pack (R149 value) — shipped with your order, not sealed inside the device box"
- Homepage, under "Brighten Your Smile — R649":
  "Free whitening gel pack (R149 value) with every order. It ships alongside your kit,
   not sealed inside the device box. Sessions are 30 minutes, done at home.
   Gel refills are available separately."
- FAQ, "How long does one kit last?":
  "The free gel pack that ships with your order holds enough for 10 to 15 applications…"

Operational consequence: **every outgoing order must have a gel pack added to it.**
That is a packing-process requirement, not a copy question. If the gel pack is ever
out of stock, the copy comes down the same day.

## Blocking — before any ad spend

- [ ] Secure gel-pack supply and build it into the packing process (see correction above).
- [x] Remove fabricated testimonials from the homepage.
- [x] Remove the About-page claim about verified reviews; "clinically-tested" also removed.
- [x] Deactivate the Test payment gateway — gone; **Yoco is Active**.

## Store

- [x] Search & Discovery installed; complementary products live on the kit page under
      "Complete your kit". Verified against the live storefront.
- [x] Real product photography on all three add-ons.
- [x] Cart-drawer upsell deployed (commit f00a9dd) and confirmed rendering on the live site.
- [x] Contact page exists at `/pages/contact-us` and is linked in the footer.
      (`/pages/contact` 404s — that handle was never used. Not a bug.)
- [x] **Desensitising Gel replaced with GLOW Whitening Pen — 2 Pack.** Live in Shopify
      as product 10394736656667, handle `glow-whitening-pen-2-pack`, R149, cost R63.
- [ ] Reverse recommendations (add-on page → kit) NOT done. The Search & Discovery
      iframe stopped accepting clicks. Low value at launch since all ads point at the
      kit. Retry later or skip.
- [ ] Confirm free delivery applies to add-ons bought on their own.
- [ ] Add-ons have 1–3 images each. More would help conversion.
- [ ] Consider a 2-device bundle at R999 for AOV.

### Product swap — why the pen, not the mouth tray

An earlier commit proposed an LED Mouth Tray 2-Pack as the Desensitising Gel
replacement. A whitening pen shipped instead, for three reasons:

1. **Margin.** Pen costs R63, sells at R149 → R86 gross (58%). The desensitising gel
   was R113 → R139, R26 gross (19%), the only sub-45% line on the store.
2. **Demand is proven.** 12K+ sold, 4.4 stars across 2,177 ratings, #1 best seller
   from that supplier. The desensitising gel had **3** sales at source.
3. **It covers the same job.** The pen is peroxide-free — willow bark, rosemary,
   coconut, malic acid — so it still answers the sensitive-teeth objection the
   desensitising gel existed to answer, without the dead margin. A spare mouth tray
   answers nothing; nobody wants a second tray before they have used the first.

**Do not also create a mouth-tray SKU** without checking with the owner first — the
slot it was meant to fill is already taken, and a fourth add-on splits attention
across the upsell row for no extra margin.

Supply risk to watch: the R63 was a Temu lightning deal showing "only 13 left".
Price and stock will move. Cost-per-item is recorded as R63 in Shopify — re-check it
before the first restock and reprice if the true landed cost lands above ~R90.

### Margin watch
| Product | Cost | Sells | Gross | Note |
|---|---|---|---|---|
| LED Kit | ~R168 | R649 | ~R440 | after the ~R40 free gel pack |
| Whitening Pen — 2 Pack | R63 | R149 | R86 | 58%, replaces the desensitising gel |
| V34 Colour Corrector | R52 | R159 | R107 | best attach margin — show first |
| Whitening Gel — 3 Syringes | R82 | R149 | R67 | also the refill SKU |

## Domain

- [ ] `glow.co.za` taken. Available: `glowteeth.co.za`, `glowwhitening.co.za`,
      `getglow.co.za`, `glowsmile.co.za`, `tryglow.co.za`, `glowkit.co.za`.
- [ ] Cheapest 3-year domain-only: Truehost ZA ~R227. Flat-price: Register Domain SA
      / Absolute Hosting ~R285.
- [ ] Shopify DNS: A -> `23.227.38.65`, CNAME `www` -> `shops.myshopify.com`.

## Payments

- [x] Yoco Active.
- [ ] Resolve PayPal "Setup incomplete", or remove it — a half-configured gateway at
      checkout costs sales.

## Meta — owner actions

- [ ] Payment method on the ad account (owner only).
- [ ] Facebook Page, Instagram link.
- [ ] Meta app in Shopify, pixel connected.
- [ ] **Verify the pixel fires** — ViewContent, AddToCart, InitiateCheckout. Observed,
      not assumed.

## Copy risks still open

- [ ] The homepage carries five customer quotes ("Excellent. The product, when used
      with the specific gel…"). If these came from the supplier's listing rather than
      GLOW's own customers, presenting them as GLOW reviews is a misrepresentation.
      One of them — "it doesn't work without the gel" — also actively undercuts the
      free-gel message. Decide: label them as supplier reviews, or remove them.
- [ ] Confirm the SA position for a peroxide cosmetic whitening product under the
      Foodstuffs, Cosmetics and Disinfectants Act 54 of 1972 before running
      claims-based ads.
