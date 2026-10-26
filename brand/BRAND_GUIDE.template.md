# <Business name> Brand Guide

> Copy this file to your project root as `BRAND_GUIDE.md` and replace every `<...>`.
> The website skills read it before any design, copy or SEO work. If something isn't
> decided yet, write "undecided" rather than deleting the line, so Claude asks you instead of guessing.

## 1. The business
- **Name (exact spelling):** <e.g. Acme Outdoor Co.>
- **Website:** <https://example.com>
- **Platform:** <BigCommerce / Shopify / WordPress + WooCommerce / Webflow / custom>
- **What we sell, in one sentence:** <...>
- **Who buys it:** <customer type, what they care about most>
- **Service area / ships to:** <e.g. USA lower 48; local service area: City, State>
- **Contact:** phone <...>, email <...>, address <...> (exactly as it should appear everywhere)

## 2. Voice
- **Sound like:** <3 adjectives, e.g. direct, knowledgeable, friendly>
- **Never sound like:** <e.g. salesy, jokey, corporate>
- **Buttons are verbs:** <e.g. "Add to cart", "Book a visit"; never "Submit" / "OK">
- **Words we always use / never use:** <...>

## 3. Claims we are allowed to make (keep these TRUE everywhere)
Every page, product, FAQ, structured-data block and SEO tool must agree with this list.
- **Shipping:** <e.g. free over $X to the lower 48; ships in 1-2 business days>
- **Returns:** <e.g. 31 days; 60 days for account holders; installed parts 15 days>
- **Warranty:** <...>
- **Payment methods:** <only the ones actually enabled>
- **Awards / ratings / certifications:** <only real, current ones>
- **Never claim:** <e.g. "in stock" in meta descriptions, "fastest shipping", competitor comparisons>

## 4. Colours
| Token | Hex | Use |
|---|---|---|
| brand-primary | <#......> | <buttons, accents> |
| brand-primary-ink | <#......> | <primary colour as TEXT on light backgrounds, if primary fails contrast> |
| surface | <#......> | <page background> |
| surface-inverse | <#......> | <dark bands: header, footer, hero> |
| ink | <#......> | <body text> |
| ink-muted | <#......> | <secondary text; must still pass 4.5:1> |
| success / warning / error | <#...> | <status only, never decoration> |

Contrast rule: body text and buttons must reach **4.5:1** (WCAG AA). Bright brand colours
(yellow, gold, lime, light orange) usually fail on white; use them on dark surfaces or as fills
with dark text, and define a darker "ink" version for text.

## 5. Typography
- **Headings:** <font family, weights>
- **Body:** <font family, weights>
- **Prices / numbers:** <font, tabular numbers yes/no>
- **Where fonts load from:** <Google Fonts / self-hosted / Adobe Fonts>

## 6. Shape, space, imagery
- **Corner radius:** <e.g. 2px for a rugged/industrial feel, 8px for soft/friendly>
- **Spacing grid:** <e.g. 4px / 8px>
- **Photo style:** <real customers' products in use, white-background product shots, etc.>
- **Logo files:** <where they live; minimum size; dark/light versions>
- **Do not:** <e.g. stock photos of people, drop shadows on text, more than 2 fonts>

## 7. Site structure that matters
- **How customers find products:** <by category / by vehicle or model / by service / by location>
- **Most important pages (money pages):** <home, top categories, top products, booking page>
- **Pages that must never be indexed:** <search results, cart, account, thank-you>

## 8. Tools and integrations on the site
List every app/script so audits can spot leftovers:
| Tool | Purpose | Still used? | Owner decision on loading |
|---|---|---|---|
| <Google Analytics 4> | analytics | yes | <after cookie consent> |
| <Meta Pixel> | ads | yes | <...> |
| <Reviews app> | reviews | yes | <...> |
| <SEO tool, e.g. Search Atlas / Yoast> | SEO | yes | <must not rewrite headings/schema without review> |

## 9. Privacy and compliance
- **Cookie banner:** <opt-in for EU/UK visitors, opt-out elsewhere / opt-in everywhere>
- **Honour Global Privacy Control:** <yes/no>
- **Accessibility target:** WCAG 2.2 AA

## 10. Owner preferences
- <e.g. "Don't redirect discontinued products; hide them so they 404.">
- <e.g. "No paid widget subscriptions.">
- <e.g. "Upload themes myself; never publish without asking.">
