---
name: website-performance
description: Improve website speed and Google PageSpeed / Core Web Vitals scores (LCP, TBT/INP, CLS, FCP) without changing the look. Use when the user mentions PageSpeed, Lighthouse, slow pages, mobile score, Core Web Vitals, or heavy scripts.
---

# Website performance

Load `brand-guide` (so speed fixes never change the brand look) and follow `website-change-safety`.

## Method
1. Baseline with PageSpeed Insights mobile, 2-3 runs per page, plus field data. Note the LCP element.
2. Find the cause in the report: Long tasks, Bootup time / third-party summary, Render-blocking
   requests, LCP breakdown (load delay vs render delay), DOM size, Forced reflow.
3. Fix one cause at a time, measure again, keep only what helps.
4. If you can, A/B locally before publishing: serve the new JS/HTML/CSS through request interception
   against the live page, and serve BOTH versions the same way (an uncompressed local file vs a
   gzipped live file skews simulated timings). Compare main-thread time, DOM size, style/layout time.

## The fixes that actually moved scores (check these first)

### Third-party and platform weight (usually the biggest)
- **Uninstalled apps that keep loading.** Remove leftover page-builder widgets and script entries.
  Some platforms keep injecting an integration after the app is removed (e.g. a visual editor runtime
  of 50+ files); look for a channel/storefront-level "Disable" switch, else ask platform support.
- **Load on demand, not on every page:** video players (show a poster image + play button, create the
  iframe on click), captchas (load when the form opens), chat widgets, loyalty/rewards widgets (only
  on the page that needs them), review widgets below the fold.
- **Embedded video blocks** added through a page builder can't be deferred by the theme; move those
  videos into the theme's own video area that uses a click-to-load facade.
- **Duplicates:** two analytics libraries, the same tag twice, an old and a new pixel.
- Don't delay ad/analytics tags until interaction without the owner's OK; it changes their data.

### JavaScript doing too much at load
- **Carousels/sliders:** desktop-first slider settings often build the desktop layout and then rebuild
  for phones; switch to mobile-first settings. "Infinite/loop" modes clone every slide 2-3x (hundreds
  of extra elements); turn looping off where it isn't needed. Initialise sliders that start below the
  first screen only when they come near the viewport (IntersectionObserver), with CSS that shows the
  un-initialised row at the same height so nothing jumps.
- **Page builders and plugins** (WordPress/Wix/Squarespace especially): each plugin may add its own
  CSS/JS to every page; disable what isn't used and load the rest only where needed.
- **Hidden duplicate markup:** e.g. listing pages that render a grid AND a hidden list view of every
  product. Render one.
- Remove leftover debug logging and dead code paths that still run.

### Largest Contentful Paint
- Identify the real LCP element. If it is a **CSS background image**, the browser finds it late;
  add `<link rel="preload" as="image" fetchpriority="high">` on that page only, with the URL
  **byte-identical** to the one the CSS resolves to (else it downloads twice).
- Only the first visible row of images gets `fetchpriority="high"` (e.g. 2 on a 2-column phone grid);
  more high-priority images split bandwidth with the real LCP image.
- Never lazy-load the LCP image. Do lazy-load everything below the fold.
- Check what format the platform already serves (many CDNs auto-convert to WebP/AVIF); re-saving
  images may gain nothing. Big wins come from oversized source images and wrong `sizes`.

### First paint / render-blocking
- The theme's main stylesheet is usually the bottleneck. Page-specific CSS can be split out or
  critical CSS inlined, but that's a larger, riskier project; propose it, don't slip it in.
- Every extra render-blocking stylesheet or sync script in `<head>` (often injected by apps) adds delay.
- Fonts: keep `font-display` choices intentional (icon fonts need `block`; text fonts can `swap`
  only if fallback metrics are close enough to avoid layout shift).

### Layout shift
- Reserve space for images (width/height), embeds (aspect-ratio box), late banners and widgets.
- Anything initialised by JS must have pre-init CSS of the same size.

## Report
Before/after numbers per page (as ranges), field data status, what changed, and what's left with
the owner's decision needed (third-party trade-offs). Remind them lab scores vary; trends and field
data matter more than one run.
