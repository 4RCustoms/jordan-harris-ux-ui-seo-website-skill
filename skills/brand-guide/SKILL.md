---
name: brand-guide
description: Create, load or check the business's BRAND_GUIDE.md (colours, fonts, voice, allowed claims, policies, tools). Use before any website design, copy, SEO or UX work, when the user mentions their brand, colours, fonts or tone, or when no brand guide exists yet.
---

# Brand guide

Every website skill in this set depends on the brand guide. Do this first.

## 1. Find it
Look for, in order: `BRAND_GUIDE.md` in the project root, `docs/BRAND_GUIDE.md`, `brand/BRAND_GUIDE.md`,
any file the user names. Read it fully. If it has `<...>` placeholders or "undecided" entries that
matter for the current task, ask the user about those specific items; don't guess.

## 2. If there is none, build a draft from the live site
1. Copy the template from this repo (`brand/BRAND_GUIDE.template.md`) to `BRAND_GUIDE.md`.
2. Fill what you can observe, and mark each filled value `(observed)`:
   - Colours: read the live CSS (custom properties, button/header/footer backgrounds). Report hex values.
   - Fonts: the `font-family` actually rendered for headings and body, and where they load from.
   - Contact details, shipping/returns/warranty wording: from the footer, policy pages and a product page.
   - Tools: every third-party script domain the home page loads (analytics, pixels, chat, reviews, SEO tools).
3. Run the contrast check below on the observed colours and note failures.
4. Hand the draft to the owner: list what was observed vs. what still needs their decision
   (voice, claims they want to make, privacy choices, preferences). Never invent claims.

## 3. Contrast check (always)
Compute WCAG contrast ratios for every text/background pair the site uses (formula: relative
luminance, (L1+0.05)/(L2+0.05)). Body text and buttons need >= 4.5:1, large text >= 3:1.
Typical finding: a bright brand colour (gold, yellow, lime) on white is around 1.5:1. Fix by keeping
the bright colour for fills/dark bands and adding a darker "ink" shade of the same hue for text.
Record the pairs and ratios in the guide.

## 4. Keep it the single source of truth
- Design work uses the guide's tokens, not new hex values. If a needed value isn't a token, propose
  adding it to the guide first.
- Copy uses the guide's voice and only the "Claims we are allowed to make".
- When you find the live site contradicting the guide (old policy numbers, removed payment methods,
  old brand colours), list it as a finding; don't silently "fix" the guide to match the site.
