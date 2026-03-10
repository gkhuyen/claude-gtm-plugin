---
name: "gtm-pricing"
description: "B2B go-to-market strategy, pricing models, ICP development, positioning, and competitive intelligence. Use when planning GTM strategy, setting pricing, defining ICP, or evaluating opportunities."
---

# GTM Strategy & Pricing

Comprehensive B2B GTM framework: ICP definition, positioning, pricing, competitive intel, and opportunity evaluation.

**Quick reference**:
- ICP scoring: 80+ = Ideal | 60–79 = Good | 40–59 = Marginal | <40 = Pass
- Positioning: `For [target] who [need], [product] is a [category] that [benefit]. Unlike [alternative], our product [differentiator].`
- Value-based price: 10–20% of quantified value delivered
- Tier structure: Good / Better (anchor) / Best

---

## Part 1: ICP Development

**Three dimensions**:

```yaml
firmographics:
  company_size: "50-500 employees"
  revenue_range: "$10M-$100M ARR"
  industry: [Primary vertical, Secondary vertical]
  geography: "North America"
  growth_stage: "Series A-C or profitable"

technographics:
  current_stack: [CRM, ERP, industry tools]
  tech_maturity: "Has CRM, considering automation"
  cloud_adoption: "Hybrid or cloud-first"

psychographics:
  pain_awareness: "Problem-aware, solution-seeking"
  change_readiness: "Has budget, executive sponsor"
  buying_process: "Committee (3-5 stakeholders)"
```

**ICP scoring** (weighted, 100 points):

| Criterion | Weight |
|-----------|--------|
| Pain point alignment | 25% |
| Company size fit | 20% |
| Industry match | 20% |
| Budget availability | 20% |
| Tech stack compatibility | 15% |

---

## Part 2: Positioning

**April Dunford Canvas**:
1. Competitive alternatives — what would customers use without you?
2. Unique attributes — what do you have that alternatives don't?
3. Value — what capability do those attributes enable?
4. Target customers — who cares most about this value?
5. Market category — what context makes value obvious?

**Messaging hierarchy**:
```
Level 1: Strategic Narrative — who we are, what we believe, why we exist
Level 2: Solution Messaging — what it does, 3 differentiators, proof points
Level 3: Persona Messaging — pain points, value props, objection handling by role
```

**Persona messaging matrix**:

| Persona | Pain Points | Value Props | Proof Points |
|---------|-------------|-------------|--------------|
| CFO | Cost visibility, compliance | ROI, audit trail | 30% cost savings case study |
| Ops Director | Manual processes, errors | Automation, accuracy | 10× faster demo |
| End User | Clunky tools | Easy to use, mobile | G2 reviews 4.8/5 |

---

## Part 3: Competitive Intelligence

**Battlecard structure** (one per competitor):
```markdown
## Competitor: [Name]
Founded | HQ | Funding | Target market | Pricing

### Strengths (acknowledge honestly)
### Weaknesses → Our opportunities
### Common objections + responses
### Win strategy: Lead with [differentiator] → Prove with [proof point] → Reference [story]
```

---

## Part 4: GTM Motion Selection

| Motion | Best For | ACV | Sales Cycle |
|--------|----------|-----|-------------|
| Product-Led | Low ACV, self-serve | <$5K | Days |
| Sales-Assisted | Mid ACV | $5–50K | Weeks |
| Enterprise | High ACV | $50K+ | Months |
| Partner/Channel | Geographic expansion | Variable | Variable |

**Launch checklist**:
- T-30: ICP documented, positioning finalized, battlecards done, sales materials ready, pricing approved
- Launch week: Press release, website updated, sales team trained, outbound sequences live
- T+30: Win/loss analysis, messaging refinement, pipeline review, competitive response documented

---

## Part 5: Pricing Strategy

**Value-based pricing process**:
1. Quantify value: time saved × hourly rate + revenue increase + costs avoided
2. Price at 10–20% of annual value delivered
3. Anchor to next best alternative (not cost)

**Value calculation template**:
```
Time savings: [hours/week × hourly rate × 52]
Revenue impact: [additional deals × deal value × 12]
Cost avoidance: [errors prevented × cost per error × 12]
Total annual value: $____

Suggested price: $[10% of value] – $[20% of value] / year
```

**Tier structure**:

| Tier | Purpose | Price | Feature gates |
|------|---------|-------|---------------|
| Good (Entry) | Remove barrier to entry | Low | Core features, limited usage |
| Better (Growth) ← ANCHOR | Where most customers land | Mid | Full features, reasonable limits |
| Best (Scale) | Capture high-value customers | 2–3× Better | API, SSO, custom branding, dedicated CSM |

**What to never gate**: security features, core functionality, data export.

**Feature gating by type**:
- Scale limits: users, projects, API calls, storage
- Sophistication: advanced automations, integrations
- Control: admin roles, SSO/SAML, audit logs

---

## Part 6: Opportunity Scoring

Score new client or project opportunities across 5 dimensions (100 points total):

| Dimension | Weight | Key Questions |
|-----------|--------|---------------|
| Market Fit | 25% | Is this our ICP? Does pain align? |
| Technical Fit | 20% | Can we actually solve this? |
| GTM Fit | 20% | Do we have the right motion/channel? |
| Personal Fit | 15% | Do we want this customer? |
| Economics | 20% | Is the ACV worth the CAC? |

**Red flags**: Stakeholders misaligned, no clear budget, outside ICP, requires significant custom work, 4+ competitors already evaluated.
