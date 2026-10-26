---
name: website-audit
description: Run a full, prioritised audit of a live website (speed, SEO, AI search, accessibility, UX, content accuracy, third-party scripts) before changing anything. Use when the user asks to audit, review, check or "make perfect" a website, or asks why a score is low.
---

# Website audit

Load the `brand-guide` skill first. The audit is read-only: change nothing on the live site.

## 1. Pick the pages
At minimum: home, the top 2 category/collection or service pages, the top 2 product/detail pages,
cart, search results, a blog post, contact, the policies page, the 404 page. Ask the owner which
pages make the money if it isn't obvious.

## 2. Measure (record numbers, not impressions)
- **Google PageSpeed Insights** (pagespeed.web.dev), mobile, for each page. Run **2-3 times**: lab
  scores swing 10-20 points run to run on the same page. Report the range.
- **Field data** at the top of the same report ("Discover what your real users are experiencing",
  Core Web Vitals pass/fail). This is what Google ranks with; lab scores are a simulated slow phone.
- Record per page: Performance / Accessibility / Best Practices / SEO, FCP, LCP, TBT, CLS, the
  **LCP element** (it is often not what you'd guess: a CSS background, a heading, the 2nd card), and
  every failing audit with its element snippets.
- Local Lighthouse is fine for accessibility/SEO/best-practices, but performance numbers on a busy
  laptop are unreliable; compare only interleaved before/after runs on the same machine.

## 3. Inventory what loads
From the HTML and network log of the home page and a product page:
- Every third-party domain and script, its size and main-thread time. Match each to the brand guide's
  tool list. Flag anything nobody owns.
- **Leftovers from uninstalled apps** are common: page-builder widgets, script-manager entries,
  injected platform integrations that keep loading after the app is "removed". Check the HTML after
  any uninstall.
- Duplicate tags (two analytics libraries, the same pixel twice, two copies of a loyalty script).
- Scripts that load on every page but are needed on one (captchas, video players, chat, reviews).

## 4. Content accuracy (often the most valuable part)
Search all pages, product descriptions, FAQs, structured data (JSON-LD) and SEO-tool output for:
return windows, shipping promises, warranty terms, payment methods, stock claims, prices, contact
details. Every value must match the brand guide's claims. Typical finds: a product FAQ saying 15 days
while the policy says 31; a removed payment method still listed; "in stock" baked into meta descriptions.

## 5. SEO and AI-search checks
Use the `website-seo` skill checklist (titles, one H1, canonicals, noindex on search/cart, crawlable
links, structured data validity and consistency, SEO tools rewriting headings or adding schema).

## 6. Accessibility and UX checks
Use the `website-ux-ui` skill checklist (contrast, keyboard access, carousels, buttons vs links,
tap targets, forms, focus, layout on 320/390/768/1024/1440px).

## 7. Report
Group findings as: **Blocker / Fix this week / Should fix / Nice to have**. For each: what a customer
experiences, the evidence (page, element, number), whether it's theme/code, content, or a store
setting/app, and the fix. Separate "already like this before our work" from "new". Lead with a
plain-English summary the owner can act on, then the details.

Never pad the report. "No problems found here" with the checks you ran is a good result.
