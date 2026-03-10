---
name: marketing-demand-acquisition
description: Multi-channel demand generation, paid media optimization, SEO strategy, and partnership programs for Series A+ startups. Includes CAC calculator, channel playbooks, HubSpot integration, and international expansion tactics. Use when planning demand generation campaigns, optimizing paid media, building SEO strategies, establishing partnerships, or when user mentions demand gen, paid ads, LinkedIn ads, Google ads, CAC, acquisition, lead generation, or pipeline generation.
license: MIT
metadata:
  version: 1.0.0
  author: Alireza Rezvani
  category: marketing
  domain: demand-generation
  updated: 2025-10-20
  python-tools: calculate_cac.py
  tech-stack: HubSpot, LinkedIn-Ads, Google-Ads, Meta-Ads, SEO-tools
  target-market: B2B-SaaS, Series-A+
---

# Marketing Demand & Acquisition

Acquisition playbook for Series A+ startups scaling internationally with hybrid PLG/Sales-Led motion.

---

## 1. Full-Funnel Framework

**TOFU (Awareness)**: Paid social thought leadership, display, content syndication, SEO informational keywords, co-webinars.

**MOFU (Consideration)**: Paid search solution keywords, retargeting, gated content, email nurture, comparison pages.

**BOFU (Decision)**: Brand + competitor keywords, direct outreach, free trial CTAs, case studies, intent-based retargeting.

**Campaign brief template**:
```
Name | Objective | Budget | Duration | Channels | Audience | Offer
Success metrics: Primary (SQLs, CPO) + Secondary (MQLs, conversion rate)
HubSpot: Campaign ID, lead scoring rules, attribution model, SLA
```

**HubSpot tracking**: UTM convention: `utm_source={channel}&utm_medium={cpc|email|organic}&utm_campaign={id}&utm_content={variant}`. Use W-shaped multi-touch attribution for hybrid motion.

---

## 2. Paid Media

### Channel Matrix

| Channel | CAC Range | CVR | Priority (Series A) |
|---------|-----------|-----|---------------------|
| LinkedIn Ads | $150–$400 | 0.5–2% | ⭐⭐⭐⭐⭐ (B2B primary) |
| Google Search | $80–$250 | 2–5% | ⭐⭐⭐⭐⭐ (high intent) |
| Google Display | $50–$150 | 0.3–1% | ⭐⭐⭐ (retargeting) |
| Meta (FB/IG) | $60–$200 | 1–3% | ⭐⭐⭐ (SMB/low ACV) |
| YouTube | $100–$300 | 0.5–1.5% | ⭐⭐ (demo/brand) |

### LinkedIn Ads Playbook

**Campaign structure**: Awareness (thought leadership) → Consideration (product education, retargeting) → Conversion (demo request).

**Targeting**: Company size 50–5,000 | Director+ titles | SaaS/Tech/Professional Services | Matched audiences (Insight Tag retargeting + email lists).

**Creative**: Thought leadership (no pitch) | Social proof (logos, case study) | Problem-solution (3-second hook) | Demo-first (show product immediately).

**Lead gen forms vs. landing pages**: Forms = 2–3× higher CVR, lower quality (TOFU/MOFU). Landing pages = lower CVR, higher quality (BOFU/demo).

**Budget scaling**: Start $50/day per campaign. Scale 20% weekly if CAC < target.

### Google Ads Playbook

**Campaign priority**: Brand terms → Competitor terms → Solution keywords → Problem keywords → Display retargeting.

**Bid strategy**: Start Manual CPC → Target CPA at 50+ conversions → Maximize Conversions at 100+. Bid 15–20% higher for EU markets.

**Ad copy (RSAs)**: 15 headlines covering value props, features, social proof, CTAs, and pinned keywords. 4 descriptions covering primary value prop, differentiators, proof, and backup.

**Negative keywords**: Maintain 100+ list (free, cheap, jobs, career, student, open source).

### Budget Allocation ($30–50k/month)

| Channel | Budget | Expected MQLs | Expected SQLs | CAC |
|---------|--------|---------------|---------------|-----|
| LinkedIn | $15k | 50 | 10 | $1,500 |
| Google Search | $12k | 80 | 20 | $600 |
| Google Display | $5k | 120 | 5 | $1,000 |
| Meta | $5k | 100 | 8 | $625 |
| Partnerships | $3k | 20 | 5 | $600 |

**Scaling rules**: CAC < target → +20%/week. CAC > target → pause + optimize. CVR drops >20% → check landing page/offer fatigue.

---

## 3. SEO Strategy

### Technical Foundation

**Must-have**: XML sitemap → Search Console | HTTPS + SSL | Core Web Vitals passing (LCP <2.5s) | Structured data (Organization, Product, FAQ) | Hreflang for international pages.

**Quarterly audit**: Crawl with Screaming Frog → fix 404s, redirect chains, duplicate content, slow pages (>3s), mobile issues.

### Keyword Tiers

| Tier | Examples | Intent | Priority |
|------|----------|--------|----------|
| BOFU | "best [category]", "[competitor] alternative" | Commercial | First |
| MOFU | "how to [solve problem]", "[use case] tools" | Informational-Commercial | Second |
| TOFU | "what is [concept]", "[industry] challenges" | Informational | Third |

**International**: Use Ahrefs/SEMrush with language filters. Translate culturally (not literally). British spelling for UK. Local domain/subdirectory for EU (domain.de > domain.com/de).

### Content Calendar (Series A minimum)

- TOFU: 4 posts/month (ultimate guides, listicles, industry reports)
- MOFU: 2 posts/month (comparisons, how-to guides, best-of lists)
- BOFU: 1 post/month (case studies, product landing pages)
- Refresh: 2 existing posts/month

### Link Building (Priority Order)

1. **Digital PR**: Publish original research → pitch journalists (HARO, Terkel, Featured)
2. **Guest posting**: DA 40+ sites only. Anchor text: 70% branded, 20% topical, 10% exact match
3. **Partnerships**: Co-branded content → mutual homepage links
4. **Community**: Reddit/Quora answers, free tools that earn natural backlinks
5. **Broken link building**: Ahrefs Broken Backlinks report → offer replacement content

---

## 4. Partnerships

### Partnership Tiers

| Tier | Target | Structure | ROI |
|------|--------|-----------|-----|
| Strategic | Complementary SaaS (overlapping ICP) | Co-marketing + integration + rev share | Very high |
| Affiliate | Bloggers, review sites, influencers | 20–30% recurring or $300–500/SQL | Medium-high |
| Referral | Existing customers | $500/closed deal or 1 month free | Medium |
| Marketplace | Shopify, Salesforce, HubSpot marketplaces | Free listing + rev share | Low-medium |

**Partner outreach**: Lead with integration value + co-marketing idea. Define scope, rev model, success metrics, 12–24 month term, 90-day exit clause.

**Affiliate commission** (Series A typical): Tier 1 influencers = 30% recurring/12 months + bonuses. Tier 2 bloggers = 20% recurring. Customers = $500/deal or 1 month free.

**Co-marketing webinar**: 6 weeks out → plan. 4 weeks out → promote (3 emails + 8–10 social posts + $2k LinkedIn ads). Day of → 60 min (40 content + 15 Q&A + record). Follow-up → recording + 3-email nurture + split leads by referral source.

**HubSpot tracking**: "Partner Source" property on contacts/deals. UTM: `utm_medium=referral&utm_source={partner-name}`. Monthly pipeline report per partner.

---

## 5. Attribution & Reporting

**Attribution model** (recommended for hybrid PLG/Sales-Led): **W-shaped** — 40% first touch, 20% mid-funnel, 40% last touch.

**HubSpot dashboards**:
- Daily: MQLs, SQLs, pipeline $ by channel
- Weekly: CAC by channel, ROAS, CPL, channel mix
- Monthly: Marketing-sourced pipeline vs. target, win rate by source

**International budget split**: EU = 40% LinkedIn, 25% Google, 20% SEO, 15% partnerships. US/CA = 35% Google, 30% LinkedIn, 20% SEO, 15% partnerships.

**GDPR compliance (EU)**: Double opt-in for email. Explicit consent tracking in HubSpot. Display prices in EUR. Local payment methods (SEPA, iDEAL).
