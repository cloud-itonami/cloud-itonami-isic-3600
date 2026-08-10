# Business Model: Community Water Safety Operations

## Classification

- Repository: `cloud-itonami-isic-3600`
- ISIC Rev.5: `3600`
- Activity: water collection, treatment and supply
- Social impact: safe water, faster leak response, transparent public reporting

## Customer

- small municipalities
- schools and campuses
- factories with water systems
- rural water associations
- disaster-preparedness groups

## Offer

- sensor and lab result ingestion
- water-quality dashboard
- maintenance and leak-response workflow
- public safety reports
- incident and audit ledger
- operator training

## Revenue

- setup fee per site
- monthly monitoring subscription
- incident-response support
- public-reporting package
- sensor integration services

| Package | Customer | Price shape |
|---|---|---|
| Managed Starter | 給水人口1–5万人（概ね4,000–20,000栓）の小規模水道事業者・簡易水道組合・自家用水道 1者 | ¥35,000/月 flat |

**Market-anchored (2026-08-10) — read the confidence caveat below before
quoting this number.** Public-infrastructure software turned out to be the most
price-opaque category surveyed in this fleet. Of 7 product families examined,
**only 2 publish figures, and only 1 of those is a commercial vendor**:

- **1water.ai** (CCR = annual Consumer Confidence Report software) — Starter
  「$299/CCR (one-time)」, Pro 「$699/CCR or $99/mo」, Full Service
  「$1,499/CCR or $149/mo」, 60-day free trial
  (<https://1water.ai/pricing>). At ~¥150/$ that is **¥14,850–22,350/月**.
- **EPA CCR iWriter and state primacy-agency templates** (Texas TCEQ,
  Wisconsin DNR, New Jersey DEP) — 「$0」, free Word-based tools
  (<https://www.tapwaterdata.com/ccr/ccr-software-pricing>).

**Non-disclosing**: **SwiftComply**'s own pricing page is a quote form
(「Tell us which programs you manage, and we'll send you a tailored quote within
one day」, <https://www.swiftcomply.com/pricing/>). **Klir** and **120Water**
require a demo/RFP. **Bynry SMART360** publishes only that it charges per meter
(「Every quote is custom-scoped against your meter count, integrations, and
rollout window」, <https://www.bynry.com/pricing>). Domestically, **E-Qias
Cloud** says 「定額の利用料金」 without a figure
(<https://www.ejk.co.jp/products/e-qias-cloud/>), and **あいちウォーターネット,
AQUASTAFF, SUIBIZ and 水道標準プラットフォーム** publish nothing. Searching
Japanese 入札/落札 records for a comparable unit (water-quality reporting and
threshold-monitoring software on its own, rather than bundled into a plant
contract) did not surface a usable public award price either.

Three things must be stated plainly rather than smoothed over:

1. **The only verifiable public prices cover a single function** — authoring and
   hosting an annual water-quality report. Nothing publicly priced covers
   jurisdiction assessment, threshold-breach screening or alert-suppression
   governance.
2. **The Klir / 120Water band is not used as a pricing basis.** Third parties
   quote $15,000–75,000/year for Klir and "mid-four to low-five figures
   annually" for 120Water, but neither is a vendor-published price — the 120Water
   source explicitly labels its own figures directional and unverified. An
   estimate about a competitor is not evidence of a market price, and this
   business model does not build on one.
3. **A free floor genuinely exists in this market.** EPA's CCR iWriter is $0.
   Any paid tier here competes against zero, not merely against a cheaper vendor.

**¥35,000/月 flat** is therefore set at roughly 1.5× the highest *verifiable*
commercial anchor (1water Full Service, ¥22,350/月), on the grounds that this
actor covers more than report authoring — jurisdiction assessment, threshold-
breach screening, a human-gated alert-suppression path that cannot be finalized
twice for the same site, and an audit ledger. It is deliberately **not** placed
in the enterprise-platform band, because this actor has **no SCADA/telemetry
ingestion, no hydraulic-modeling engine and no LIMS/GIS integration**, and
because that band has no published price to anchor to. Pricing is flat rather
than per-meter so a small utility can budget it as a line item against a market
whose floor is free. **Confidence in this figure is low** — it rests on one
commercial vendor's list price. It should be revised as soon as a second
verifiable anchor (a vendor list price or a public procurement award for a
comparable scope) is found; it is a starting point, not a validated market
position.

**Subscribe (2026-08-10)**: a live Stripe Payment Link for the Managed Starter
tier (¥35,000/月 flat) is available now — [**subscribe to Managed
Starter**](https://buy.stripe.com/3cIeVe4UnaByghWa66eEo0a). This is a no-code
Stripe-hosted checkout; nothing in this repo's actor code changed. After
subscribing, contact gftdcojp to arrange managed-tenant setup (manual
fulfillment today, no automated onboarding yet). **No utility has claimed or
subscribed to this tier yet — this is a live, working checkout with zero paid
tenants, not a claim of existing revenue.**

## Trust Controls

- safety thresholds cannot be weakened without review
- a fabricated jurisdiction citation, incomplete evidence, an out-of-
  range contaminant reading, or an unresolved threshold breach -- each
  forces a hold, not an override
- public reports require source evidence
- alert suppression is logged and escalated, and cannot be finalized
  twice for the same site: a double-suppression attempt is held off
  this actor's own site facts alone, with no upstream comparison
  needed
- real-time emergency paths remain outside LLM control
