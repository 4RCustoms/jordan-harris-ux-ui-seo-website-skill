---
name: website-ux-ui
description: Design, redesign or review website pages and components so they are on-brand (per BRAND_GUIDE.md), usable on phones, and accessible (WCAG 2.2 AA). Use for page layouts, product/category pages, navigation, carousels, forms, buttons, colour/typography choices, or accessibility fixes.
---

# Website UX / UI

Load `brand-guide` first and use its tokens, fonts, radius, voice and imagery rules. If a value
you need isn't in the guide, propose adding it rather than inventing one.

## Design principles
- **Customers scan for "is this for me" first** (right service, serves my area, fits my product),
  then price/next step. Put that and the primary call to action (call / quote / book / buy) where
  the eye lands, and keep it in reach on phones; match navigation to how customers actually shop (by model, service,
  location) as recorded in the guide.
- **Bright brand colours live on dark surfaces** or as fills with dark text; text uses the "ink" shade.
- One primary action per view; buttons are verbs.
- Motion only on `transform`/`opacity`, 150-250ms, and respect `prefers-reduced-motion`.
- Every layout works at 320, 390, 768, 1024 and 1440px with no sideways scroll.
- Don't let floating widgets (chat, rewards, ratings badge, cookie banner) collide; check each corner
  on phone and desktop, and give each widget a home.

## Accessibility checklist (the issues that actually fail Lighthouse/axe)
- Contrast >= 4.5:1 for text and buttons.
- **Buttons vs links:** actions are `<button type="button">`; navigation is `<a href>`. Icon-only
  controls get an `aria-label`. If visible text changes (Read more/Read less), change the label too.
- Toggles expose state with `aria-expanded` and point to what they control with `aria-controls`.
- Visible focus indicator on every interactive element (don't remove outlines globally).
- **Tap targets >= 24x24px** (padding or negative-margin tricks keep the visual size).
- **Carousels:** hidden slides must not be tabbable (tabindex -1 on everything inside slides that
  are off-screen, including during the slide animation); only real links/buttons count as focusable
  (`a[href]`, not any `[href]`, or SVG `<use href>` icons become empty tab stops); arrows have names;
  autoplay has a pause control.
- Lists stay lists: if a script wraps list items in divs, use `role="presentation"` or real divs.
- `<iframe>` has a `title`. Native `<select>` has no ARIA role. Every input has a `<label>`.
- Modals: focus moves in, Escape closes, focus returns to the trigger.

## UX decisions to bring to the owner (don't decide alone)
- Removing a feature customers can see (e.g. grid/list toggle, a tab, a slider loop).
- Moving content (e.g. videos from a tab to a section), changing policy wording, ending a programme.
- Anything that changes what tracking/analytics record.
Offer 2-3 options with a recommendation and the trade-off in plain English.

## Verify
Screenshot each changed component at phone and desktop widths, run Lighthouse accessibility, tab
through with the keyboard, and check nothing shifts while loading (CLS ~0).
