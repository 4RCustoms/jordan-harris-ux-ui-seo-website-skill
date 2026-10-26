# Jordan Harris UX / UI / SEO Website Skill

A set of [Claude Code](https://claude.com/claude-code) skills for improving a business website's
**design, usability, accessibility, speed and SEO**, built around **your own brand guide** so the
work always looks and sounds like your business.

It was distilled from a real production overhaul of a live business website (theme rebuild,
PageSpeed work, SEO/AI-search cleanup, accessibility fixes, third-party script audits). Everything
here is general and works for **service businesses** (leads, calls, bookings) as well as online
stores, on WordPress, Webflow, Wix, Squarespace, Shopify, BigCommerce or a custom site.

## What's inside

| Skill | Use it when you want to... |
|---|---|
| `brand-guide` | Set up or check your brand guide (colours, fonts, voice). Every other skill reads it first. |
| `website-audit` | Get a full, prioritised report on a site before changing anything. |
| `website-performance` | Raise the PageSpeed score and make phones load faster. |
| `website-seo` | Fix SEO, local SEO and AI-search issues: titles, schema, Google Business Profile, service-area pages, content accuracy. |
| `website-conversions-kpis` | Set KPIs, make sure calls/forms/bookings are tracked, and raise the conversion rate. |
| `website-ux-ui` | Design or review pages so they're on-brand, usable and accessible. |
| `website-change-safety` | Make changes to a live store/site without breaking or losing anything. |

## Install

1. Install Claude Code (desktop app, CLI or VS Code extension).
2. Download the latest ZIP from **[Releases](../../releases/latest)** (or green **Code** button >
   **Download ZIP**, or `git clone`).
3. Copy the folders inside `skills/` into one of:
   - `~/.claude/skills/` to use them in every project, or
   - `<your-project>/.claude/skills/` to use them in one project.
4. Fill in your brand guide: copy `brand/BRAND_GUIDE.template.md` to your project as
   `BRAND_GUIDE.md` (project root) and replace every `<...>` placeholder. Or just ask Claude:
   *"Use the brand-guide skill to build my brand guide from my website."*

## Use

Talk to Claude normally; the skills load when the task matches. Examples:

- "Audit https://example.com for speed, SEO and accessibility and give me a prioritised list."
- "Our mobile PageSpeed is 40. Get it up without changing how the site looks."
- "Set up our KPIs and check that calls, quote forms and bookings are tracked in GA4."
- "Build service pages and service-area pages for local SEO."
- "Check every page for guarantees or prices that contradict each other."
- "Redesign the category page so it matches our brand guide."

## The rules these skills follow

1. **Brand guide first.** Colours, fonts, voice and claims come from `BRAND_GUIDE.md`, never guesses.
2. **Measure, change, measure again.** No "should be faster" without before/after numbers.
3. **Back up before touching anything live**, and write down how to undo it.
4. **Ask the owner before anything customers would notice** (removing features, changing policy
   wording, turning off apps).
5. **Plain English.** The owner may not be a developer; every report explains what changed and why.

## License

MIT. Use it, share it, change it.
