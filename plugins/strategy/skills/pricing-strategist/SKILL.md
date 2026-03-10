---
name: pricing-strategist
description: Design and optimize pricing strategies for SaaS products including tiering, packaging, value metrics, and experimentation. Use when setting initial pricing, optimizing conversion, expanding revenue, or when users ask about pricing strategy, monetization, or revenue optimization.
license: Complete terms in LICENSE.txt
---

# Pricing Strategist
Design pricing strategies that maximize revenue while keeping customers happy.

## Core Principles

1. **Pricing is a growth lever**: 1% improvement in pricing = 11% improvement in profit (McKinsey)
2. **Price to value, not cost**: Charge based on value delivered, not what it costs you
3. **Simple > Clever**: 3 tiers beats 5 tiers; clear packaging beats complex
4. **Experiment continuously**: A/B test, iterate, optimize

---

## Step 1: Choose Your Value Metric

Good value metrics align with customer value, are easy to understand, and grow naturally with usage.

| Metric | Value Alignment | Simplicity | Predictability | Growth |
|--------|----------------|------------|----------------|--------|
| Per User | High | High | High | Medium |
| Usage-Based | High | Medium | Low | High |
| Per Feature | Medium | High | High | Low |
| Transactions | High | Medium | Medium | High |
| Storage | Low | High | Medium | Medium |

**Examples**: Slack (per active user), Twilio (per API call), Dropbox (storage).

---

## Step 2: Choose Your Pricing Model

| Model | Pros | Cons |
|-------|------|------|
| **Flat Rate** ($99/mo, unlimited) | Simple to sell | Leaves money on table |
| **Tiered** (Starter/Pro/Business) | Captures segments, clear upsell | Anchor pricing matters |
| **Usage-Based** ($0.01/call) | Perfect value alignment, low barrier | Unpredictable revenue |
| **Hybrid** ($49/mo + $0.50/extra user) | Predictable base + scales | More complex to explain |

---

## Step 3: Design Three Tiers

**The Rule of 3**: Starter (50–60% of customers) → Pro/sweet spot (30–40%) → Business/Enterprise (5–10%).

**Anchor pricing**: Middle tier 3–4x starter price; top tier 2–3x middle. This makes the middle tier feel like the obvious choice.

```
Starter:  $29/mo  — core features, 5 users, email support
Pro:      $99/mo  — everything + integrations, 20 users, priority support  ← Most Popular
Business: $299/mo — everything + SSO, unlimited users, dedicated support
```

**Feature gating**:
- Gate by volume (users, projects, API calls)
- Gate by sophistication (advanced analytics, integrations, automation)
- Gate by control (SSO/SAML, audit logs, custom roles)
- **Never gate**: Core functionality, security features, data export

---

## Pricing Psychology

**Charm pricing**: $99 feels ~20% cheaper than $100.

**Anchoring**: Show expensive tier first or highlight "60% choose Pro."

**Annual discounts**: 15–20% off (2 months free) — improves cash flow, reduces churn, raises LTV. Offer at signup, after 2–3 months, and during renewal.

**Free Trial vs Freemium**:
- B2B SaaS → 14-day free trial (clear conversion point, no freeloaders)
- Viral products with network effects → Freemium (build user base, word of mouth)
- High-touch sales → Free trial + demo

---

## Pricing Experiments

**What to A/B test**: Price points, tier packaging, billing frequency, free trial length, anchor tier.

**Sample sizes**: ~1,000 visitors/variant to detect 10% change; ~5,000 for 5% change.

**Metrics**: Conversion (trial → paid), ARPU, CAC, LTV, payback period.

**Price increases**: Raise every 12–18 months as you add value. Communicate 30+ days in advance. Grandfather existing customers for 12 months or offer annual lock-in at current price.

---

## Revenue Expansion

**Upsell triggers**:
- User hits usage limit → show upgrade prompt immediately
- User clicks locked feature → show upgrade at moment of value
- User active 30+ days on starter → "power user" upgrade nudge

**Add-ons** (use when feature has standalone value, not everyone needs it):
```
Base plan: $99/mo
+ Extra users: $10/user/mo
+ Advanced analytics: $49/mo
+ White label: $99/mo
+ Priority support: $199/mo
```

---

## Pricing by Segment

| Segment | Price Point | Sales Motion | Decision Maker | Sales Cycle |
|---------|-------------|--------------|----------------|-------------|
| SMB | $29–99/mo | Self-serve | End user/team lead | Minutes–days |
| Mid-Market | $99–999/mo | Self-serve + light touch | Dept head | Days–weeks |
| Enterprise | $1,000+/mo | High-touch sales | VP/C-level | Weeks–months |

---

## Key Metrics

| Metric | Healthy Benchmark |
|--------|------------------|
| Trial → Paid conversion | >15% |
| MRR Growth (early stage) | >10%/month |
| Churn Rate | <5%/mo (SMB), <1%/mo (enterprise) |
| LTV:CAC | >3:1 |
| Payback Period | <12 months |
| Net Revenue Retention | >100% |

---

## Pricing Page Best Practices

**Structure**: Hero ("Pricing that grows with you") → 3-tier comparison table → FAQ (Can I change plans? Refunds? Cancel anytime?) → Trust signals (testimonials, logos, guarantee).

**Psychology**: Highlight "Most Popular" on middle tier with larger CTA button; show annual/monthly toggle with savings badge; include one social proof quote near CTA.

---

## Checklists

**Launching pricing**:
- [ ] Pick value metric; design 3 tiers with anchor prices (3–4x between tiers)
- [ ] Package features (60% / 85% / 100%); offer 14-day trial; set up Stripe billing

**Optimizing pricing**:
- [ ] Track conversion rates by tier; survey customers on pricing perception
- [ ] A/B test price points; add annual billing option; create in-app upgrade prompts
- [ ] Monitor NRR; review pricing every 6–12 months

---

## Common Pitfalls

- **Pricing too low**: Harder to raise than lower; undermines perceived value
- **Too many tiers**: 5+ tiers confuses buyers; stick to 3
- **Gating core value**: Don't lock what makes your product worth using
- **Complex value metric**: Users shouldn't need a calculator to predict their bill
- **Never raising prices**: Customers expect prices to rise as you add value
