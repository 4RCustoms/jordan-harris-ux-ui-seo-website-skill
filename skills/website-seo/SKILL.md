---
name: website-seo
description: Fix technical and local SEO and AI-search (AIO/GEO) issues and content accuracy: titles, meta descriptions, headings, canonicals, indexing, crawlable links, structured data/schema, Google Business Profile, service-area pages, SEO-tool side effects. Use when the user mentions SEO, Google ranking, AI search, schema, meta descriptions, Search Console, or Lighthouse SEO.
---

# Website SEO and AI search

Load `brand-guide` first: every claim in titles, descriptions, FAQs and schema must match its
"Claims we are allowed to make". Follow `website-change-safety` for anything live.

## Technical checklist (per page type)
- Exactly one `<title>`, one meta description, one canonical, one visible or screen-reader `<h1>`.
- Headings in order (no `h3` straight after the `h1` in templates you control).
- `noindex,follow` on internal search results, compare pages, cart/account/thank-you; nothing else.
- **Crawlable links:** every `<a>` has a real `href`. Controls that do something on the page
  (toggles, print, "read more", dropdowns) are `<button type="button">`, not `<a href="javascript:...">`
  or href-less anchors. A disabled link with no href needs `role="link"` + `aria-disabled="true"`.
- No duplicate `id`s; no hidden duplicate content (e.g. a hidden list view repeating every product).
- Images have meaningful `alt`; decorative ones `alt=""`.
- Discontinued products/pages: decide with the owner (redirect to the closest replacement vs. hide
  and let it 404). Don't pick silently.

## Structured data (JSON-LD)
- Organization/LocalBusiness on the home page with name, URL, logo, contact, sameAs (real profiles).
- Service pages: Service schema (name, provider, areaServed). Stores: Product + Offer on product pages: price, currency, availability, and if used, shipping and
  return-policy fields (e.g. `merchantReturnDays`) that **match the written policy**.
- BreadcrumbList, FAQPage only where the questions are visibly on the page, Article on blog posts.
- One source of each type per page: SEO plugins/tools often add a second, conflicting schema block.
  Keep one, roll back the other.
- Validate with Google's Rich Results Test and Schema.org validator.

## SEO tools that rewrite the site
Tools that inject changes at runtime (auto meta descriptions, heading rewrites, alt text, FAQ/NLP
blocks, schema) need a review:
- Pull the tool's list of changes per URL. Keep genuinely useful content; roll back anything that
  replaces a heading or title with a *different page's* title, adds unverifiable claims ("in stock",
  "fastest", "free shipping" when it isn't), or duplicates schema.
- Check its runtime cost in PageSpeed; if the owner requires the tool's script to stay exactly as
  installed, respect that and work through its dashboard instead.

## Content accuracy sweep
Grep every service/product description, FAQ widget, policy page and meta description for: guarantees,
response-time promises, prices, licenses, return/shipping terms, payment methods, hours, contact details. List every
contradiction with the brand guide, then fix with the owner's wording. One wrong number on one
product page undermines the policy page and the schema.

## Local SEO (service businesses)
- **Google Business Profile:** correct primary category, services, service area, hours, photos,
  website link with UTM, posts; reply to reviews. Ask the owner for access; don't create profiles.
- **NAP consistency:** name, address (or service area), phone identical on the site, Business Profile,
  Yelp/BBB/industry directories. List mismatches.
- **One page per service** and per main service area, each with unique, genuinely local content,
  title like "<Service> in <City> | <Business>", internal links between related services/areas.
- **LocalBusiness schema** (the most specific subtype, e.g. Plumber, HVACBusiness) with areaServed,
  openingHours, telephone, priceRange, aggregateRating only if reviews are shown on the page.
- **Reviews:** a simple way to ask happy customers for Google reviews; never gate or fake reviews.
- **Click-to-call** and maps embed/link on contact and location pages.
- Never link client/partner sites to each other in a network, and never copy one business's
  content to another's site.

## AI search (ChatGPT, Gemini, Perplexity, Google AI Overviews)
- Clear factual pages: what you sell, who it fits, prices, policies, location; in plain text, not
  only in images or scripts.
- Consistent business facts everywhere (name, address, phone, hours, policies).
- FAQ content that answers real customer questions in a sentence or two.
- Don't block reputable AI crawlers in robots.txt unless the owner wants that; note any platform
  "agentic commerce" features and keep them working.

## Report
Per issue: page, what Google/AI tools see, the fix, and whether it's code, content or a setting.
