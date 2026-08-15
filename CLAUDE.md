# GLOW — store context for any Claude session

Read this first. It exists so a fresh session is productive in one turn instead of ten.

## The business

GLOW sells one product plus add-ons in **South Africa**, on Shopify.

- Store: `i598kh-1p.myshopify.com` · Theme: Dawn 16.0.0 · Currency **ZAR** · Timezone **GMT+2**
- Owner: Sisekelo Zulu. Claude acts as general manager: Claude does the work, the owner authorises.
- Meta Business portfolio: **GLOW Whitening SA**, `business_id=1087447840804837`

### Catalogue and economics

| Product | Price | Cost | Handle |
|---|---|---|---|
| GLOW Professional LED Teeth Whitening Kit | R649 | R149 | `glow-professional-led-teeth-whitening-kit` |
| GLOW Whitening Gel — 3 Syringes | R149 | ~R40 | `glow-whitening-gel-3-syringes` |
| GLOW Desensitising Gel | R139 | ~R35 | `glow-desensitising-gel` |
| GLOW V34 Colour Corrector | R159 | ~R40 | `glow-v34-colour-corrector` |

Main kit: Yoco fee 2.9% + R0.50 = R19.32. **Gross profit R480.68.** Break-even CPA R481. Scale CPA target under R240.

## Hard rules — do not break these

### Advertising claims
A competitor (HiSmile) was **banned by the UK ASA** for exactly the claims that used to be in these files. Never write:
- "clinically proven" / "clinically tested"
- any timeframe-to-result promise — "results in one session", "whiter in 10 minutes"
- "same results as the dentist" / "same formula"
- "FDA approved" / "SAHPRA approved"
- invented star ratings or review counts
- second person about the viewer's body — "your yellow teeth". Meta's personal-attributes rule. Use first person.

Safe and true: price comparison (R3,500–R8,000 clinic vs R649), free SA delivery, 30-day money-back, cordless/rechargeable, 30-minute sessions.

South Africa's ARB ruled against Sensodyne in May 2026 over a scoped claim with an undersized disclaimer. Any superiority claim needs a disclaimer as prominent as the claim.

### Product facts
- Sessions are **30 minutes**, not 10. The supplier diagram says 30.
- Whitening gel is presented as **included free (R149 value)**. This is only true if gel is actually packed in every kit — the supplier's own image says "(Not including gel)". **If gel is not sourced and included, this line must come down.** It is a CPA s41 false-representation risk otherwise.
- Never add a struck-through "was R798" price. The kit has never sold at R798; a fabricated reference price is a separate compliance problem from a genuine "free item worth R149" callout.

## How the theme works

The theme lives in this repo and syncs to Shopify automatically. **Edit files here, commit to `main`, Shopify picks it up in 30–60 seconds.**

Do **not** try to use the Shopify theme editor — it renders in a cross-origin iframe with closed shadow DOM, so screenshots come back blank and the accessibility tree is empty. Five sessions were lost to this. The repo is the way.

**Products are not in this repo.** Products, pages, navigation, policies and shipping are Shopify data, edited in Shopify admin.

### Verify, never assume
After any theme change, check the real storefront:

```
GET https://i598kh-1p.myshopify.com/            → expect 200
GET https://i598kh-1p.myshopify.com/products.json → check price/available/images
```

Assert on HTTP status and rendered CSS variables (`--color-button: 74,144,226`, `--buttons-radius: 6px`). Do not judge by screenshot alone.

## Gotchas that have already cost time

1. **`config/settings_data.json` is fragile.** One invalid value makes Shopify reject the whole file and silently fall back to schema defaults — no colour schemes, no brand styling. Two real examples that broke it: `animations_hover_elements: "none"` (not a valid option) and `card_shadow_opacity: 8` (the range steps by 5). **Validate every value against `config/settings_schema.json` — type, select options, and range min/max/step — before committing.**
2. **Never reference a `shopify://shop_images/...` file that isn't uploaded.** An unresolvable file reference stops the template compiling and the page returns a hard 404. The homepage hero was down for this reason. Prefer Liquid that reads existing store data, e.g. `all_products['handle'].featured_image`.
3. **New Shopify products default to inventory-tracked with quantity 0**, which shows "Sold out". Turn inventory tracking **off** for dropshipped items.
4. **Shopify's media uploader hides its file input in shadow DOM.** Walk `shadowRoot` recursively, move the input into the light DOM, then upload — do not click "Upload new", which opens a native dialog nothing can control.
5. **Shopify's rich-text code view freezes** if you paste a very large HTML string in one action. Type in chunks of roughly 100 characters with a pause between.
6. **GitHub web upload**: `/upload/main/<folder>` preserves folder structure, max 100 files per commit. Wait for "Uploading N of M" to finish before clicking Commit, or the commit is silently discarded. Click the commit button by coordinate — ref-based clicks land on the wrong element.

## Brand

Blue `#4A90E2` · Navy `#2C3E50` · Pale blue `#E8F1FF` · Gold `#D4AF37` · 6px buttons · 12px cards · cart drawer, not cart page.

## Where the rest lives

Project docs (claude.ai Project "general manager"), numbered `claude/NN-*.md`. Key ones: `06` pricing, `16` add-on research, `18` the gel/contents problem, `19` the GitHub build, `20` week-1 creative pack, `21` remaining work.
