---
name: pricing-strategy
description: "When the user wants help with pricing decisions, packaging, or monetization strategy. Also use when the user mentions 'pricing,' 'pricing tiers,' 'freemium,' 'free trial,' 'packaging,' 'price increase,' 'value metric,' 'Van Westendorp,' 'willingness to pay,' or 'monetization.' This skill covers pricing research, tier structure, and packaging strategy."
---

# Pricing Strategy

Expert guidance on SaaS pricing, value metrics, tier structure, and pricing research methodology.

## Before Starting

Gather: product type, target market (SMB/mid-market/enterprise), GTM motion (self-serve/sales-led/hybrid), primary value delivered, competitive pricing, current conversion rate and ARPU, pricing goals (growth vs. revenue vs. profitability).

---

## Pricing Fundamentals

**Three axes**: Packaging (what's in each tier) + Value metric (what you charge for) + Price point (the amount).

**Value-based pricing**: Price between the next best alternative and perceived value. Cost is a floor, not a basis.

```
Perceived value of your solution: $1,000
Your price:                        $500  ← capture value here
Next best alternative:             $300  ← your floor
Your cost to serve:                 $50
```

---

## Pricing Research Methods

### Van Westendorp Price Sensitivity Meter

Ask 100–300 respondents four questions:
1. Too expensive — would not buy
2. Too cheap — would question quality
3. Expensive but would consider
4. Bargain / great value

**Key intersections**:
- PMC (Point of Marginal Cheapness): "Too cheap" × "Expensive" → lower bound
- PME (Point of Marginal Expensiveness): "Too expensive" × "Cheap" → upper bound
- OPP (Optimal Price Point): "Too cheap" × "Too expensive" → best price
- IDP (Indifference Price Point): "Expensive" × "Cheap" → acceptable midpoint

**Acceptable range**: PMC → PME. **Optimal zone**: OPP → IDP.

### MaxDiff / Feature Importance

Show sets of 4–5 features; ask "most important" and "least important." Results rank features by utility score:

| Utility | Packaging Decision |
|---------|-------------------|
| Top 20% | Include in all tiers (table stakes) |
| 20–50% | Use to differentiate tiers |
| 50–80% | Higher tiers only |
| Bottom 20% | Cut or premium add-on |

### Willingness to Pay

- **Gabor-Granger**: Show price → "Would you buy at $X?" (Yes/No). Vary price across respondents to build demand curve.
- **Conjoint analysis**: Show bundles at different prices; respondents choose preferred option.

---

## Value Metrics

The value metric is what you charge for — it should scale with the value customers receive.

| Metric | Best For | Examples |
|--------|----------|---------|
| Per user/seat | Collaboration tools | Slack, Notion |
| Per usage/consumption | Variable workloads | AWS, Twilio |
| Per contact/record | CRM, email tools | Mailchimp, HubSpot |
| Per transaction | Payments, marketplaces | Stripe, Shopify |
| Flat fee | Simple, bounded products | Basecamp |
| Revenue share | High-value outcome tools | Affiliate platforms |

**Choosing your metric**: Analyze which usage patterns predict retention and expansion in your highest-LTV customers. If "more of X = more value," X is your metric.

---

## Tier Structure

**2 tiers**: Clear SMB vs. Enterprise split. Simple but may leave money on table.

**3 tiers** (industry standard): Good → Better (recommended) → Best.

**4+ tiers**: More granularity for wide customer size range; risk of decision paralysis.

### Good-Better-Best Framework

| Tier | Purpose | Price | Target |
|------|---------|-------|--------|
| **Good** (Starter) | Remove barriers to entry | Low, accessible | Small teams, trial converts |
| **Better** (Pro) | Where most customers land | Anchor price | Growing teams |
| **Best** (Business) | Capture high-value customers | 2–3× Better | Larger teams, power users |

### Differentiation Strategies

- **Feature gating**: Basic features everywhere; advanced features in higher tiers
- **Usage limits**: Same features, different limits (users, storage, API calls)
- **Support level**: Email → Priority → Dedicated CSM
- **Access/customization**: API, SSO, custom branding for enterprise tiers

---

## Freemium vs. Free Trial

| | Freemium | Free Trial |
|-|----------|-----------|
| **Best for** | PLG, wide top of funnel | Sales-led, high-ACV |
| **Conversion** | 2–5% free → paid | 15–25% trial → paid |
| **Risk** | Free riders, support cost | Shorter window to prove value |
| **Use when** | Network effects, viral growth | Complex product needing onboarding |

---

## Pricing Psychology

- **Anchor effect**: Show highest tier first to anchor perception
- **Charm pricing**: $49 vs. $50 (perceived as significantly cheaper)
- **Decoy pricing**: Add a "bad" middle option to push customers to "best"
- **Annual vs. monthly**: Offer 15–20% discount for annual (improves LTV and reduces churn)
- **Per user transparency**: Show total cost at common team sizes (e.g., "5 users = $X/mo")

---

## Common Pricing Mistakes

- Pricing on cost, not value
- Too many tiers (analysis paralysis)
- Feature gates customers don't care about
- Ignoring price sensitivity by segment
- Never testing or iterating on pricing
- Burying the price page (hiding = distrust)

---

## Price Increase Playbook

1. **Quantify value** delivered since last price (new features, outcomes, benchmarks)
2. **Grandfather existing customers** for 3–6 months
3. **Communicate early** (60-day notice minimum)
4. **Frame as investment** not cost increase — tie to ROI
5. **Offer annual lock-in** before increase date to capture cash
6. **Monitor churn** closely for 90 days post-increase
