---
name: website-conversions-kpis
description: Define and track the website's KPIs and conversions (calls, form leads, bookings, quote requests, purchases) and improve conversion rate. Use when the user mentions leads, conversions, KPIs, goals, analytics, GA4, Search Console, call tracking, booking, "get more customers from the site", or CRO.
---

# Conversions and KPIs

Load `brand-guide` first: section "Business model and goals" says whether this is a service business
(leads, calls, bookings) or a store (purchases), and which actions count as a conversion.

## 1. Agree the KPIs with the owner (write them into BRAND_GUIDE.md)
Pick a small set, each with where it's measured:

| KPI | Service business | Store | Where |
|---|---|---|---|
| Primary conversions | calls, quote/contact form submits, bookings | orders, revenue | GA4 key events / booking tool / call tracking |
| Conversion rate | leads / sessions | orders / sessions | GA4 |
| Cost per lead / order | ad spend / leads | ad spend / orders | ad platforms + GA4 |
| Lead quality | % of leads that became jobs | refund/return rate | CRM or owner's notes |
| Organic visibility | clicks, impressions, avg position for money keywords | same | Google Search Console |
| Local visibility | Business Profile calls, direction requests, website clicks | n/a | Google Business Profile insights |
| Speed / experience | Core Web Vitals pass (field data) | same | PageSpeed Insights |

Report monthly against last month and the same month last year. Seasonal businesses need YoY.

## 2. Make sure every conversion is actually tracked
Audit before trusting any number:
- **Click-to-call:** every phone number is a `tel:` link; clicks fire a GA4 event (e.g. `phone_call_click`).
  For real call counts use call tracking (dynamic number insertion) if the owner wants it.
- **Forms:** a successful submit (not the button click) fires `generate_lead` / a key event.
  Send people to a thank-you page or fire on the success message. Test with a real submission.
- **Bookings:** the booking tool's confirmation fires a GA4 event (most tools have a GA4/GTM integration).
- **Email clicks, directions, chat starts:** optional secondary events.
- **UTM tags** on every ad, email and social link so sources are attributable.
- Mark the right events as **Key events** in GA4; link GA4 to Google Ads and Search Console.
- Consent: tags respect the cookie banner / Consent Mode; note that opted-out visitors won't be counted.
- Never record personal data (names, emails, phone numbers) in analytics events or URLs.

## 3. Raise the conversion rate (service-business focus)
- **One clear primary action per page**, the same everywhere: "Call now", "Get a free quote" or
  "Book online". Visible above the fold on phones; sticky call/quote bar on mobile.
- **Phone number** in the header, tappable, with hours ("Open now", "24/7 emergency" only if true).
- **Short forms:** name, phone or email, what they need, ZIP/location. Each extra field costs leads.
  Say what happens next ("We'll call within 1 business hour").
- **Trust near the action:** real reviews with names/locations, license/insurance numbers, years in
  business, guarantees (only claims in the brand guide), photos of real work and team.
- **Service pages that sell:** what the service is, who it's for, typical price range or "free
  estimate", process steps, FAQs, area served, CTA. One page per main service.
- **Location/service-area pages** with genuinely local content (not copy-paste with the city swapped).
- **Speed matters most on phones** (see `website-performance`): most service searches are mobile and urgent.
- Test changes one at a time and compare conversion rate over equal periods (or a proper A/B test).

## 4. Report
Plain-English monthly summary: leads/orders by source, conversion rate, what changed on the site,
what to try next. Flag tracking gaps before drawing conclusions from the numbers.
