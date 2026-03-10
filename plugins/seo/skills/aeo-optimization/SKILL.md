---
name: aeo-optimization
description: Use this skill when optimizing for AI Engine visibility through semantic triples, page templates, and content clusters to earn AI citations
---

# AI Engine Optimization (AEO)

Optimize content for AI engines (ChatGPT, Claude, Perplexity, Google AI Overviews) so your brand gets cited in AI-generated answers.

**Why now**: 58% of Google searches = zero clicks (AI overviews). 70% of consumers use ChatGPT for searches. Best answer > best page ranking.

---

## How AI Engines Choose Content

**1. Consensus** — Facts repeated across multiple credible sources get trusted.
- Repeat key facts consistently across your own pages
- Use same terminology as industry leaders
- Build internal content clusters that reinforce each other

**2. Information gain** — Net-new insight beats generic advice.
- Original research and data
- Concrete examples with specifics
- Expert quotes with credentials
- Case studies with metrics

**3. Entities & structure** — Clear entities reduce ambiguity and boost quotability.
- Use semantic triples (Subject → Verb → Object)
- Clear headings with entity names
- Schema markup (Article, FAQ, Product)
- Short paragraphs (2–4 sentences)

---

## Semantic Triples (Most Important Technique)

Compact, unambiguous facts AI can't misread.

**Pattern**: `[Subject]` `[specific verb]` `[concrete object]`.

```
✅ GOOD
- HubSpot CRM syncs contact and company data.
- Lead Scoring assigns priority based on engagement.
- Workflows trigger email sequences from events.

❌ BAD
- The system helps with various tasks.
- It can do many things for users.
- This improves overall performance.
```

**Checklist for every key claim**:
- Subject = clear entity (product, feature, brand)
- Verb = specific and active
- Object = concrete and measurable

---

## Paragraph Pattern: Feature → How → Outcome

```
[Feature] helps [User/Role] with [Job].
It [mechanism/inputs] to [process].
Teams see [metric/result] in [timeframe/context].

Triples:
- [Subject] [verb] [object].
- [Subject] [verb] [object].
```

**Example**:
> Lead Scoring helps sales teams prioritize prospects. It combines page views, email engagement, and firmographic data to assign a numeric score, then auto-enrolls high scorers into follow-up sequences. Reps focus on qualified accounts and book 40% more meetings.
>
> - Lead Scoring assigns scores from engagement data.
> - High scorers trigger automated follow-up sequences.

---

## Page Templates

### Template 1: Category Explainer
**Goal**: Define the category, tie it to your product, earn citations.

```markdown
# What is [Category]? — [1-2 line value promise]

## What is [Category]? (~80 words)
[Plain definition. Name adjacent entities.]
Triples: 1. [S] [V] [O]. 2. [S] [V] [O].

## Why it matters now (~60 words)
[One paragraph. Tie to buyer outcomes.]

## How to apply it (3-5 bullets)

## FAQ
**Q:** [Question]?  **A:** [~1 sentence]

Schema: Article + FAQ. Author + last updated.
CTA: [Demo / Template / Signup]
```

### Template 2: Product & Feature Page
**Goal**: Clarify capability and fit; reinforce category linkage.

```markdown
# [Product/Feature] — [Outcome in 3-5 words]
**[Product/Feature] enables [Outcome] for [User/Role].**

## [Feature Area 1]
[2-4 sentences: Feature → How → Outcome]
Triples: 1. [S] [V] [O]. 2. [S] [V] [O].

## FAQ  **Q:** [Question]?  **A:** [~1 sentence]

Schema: Article + FAQ. Author + last updated.
Links: Back to [Category Explainer] | Forward to [Demo/Trial]
```

### Template 3: Comparison / Alternatives Page
**Goal**: Help readers decide with clear criteria; earn fair citations.

```markdown
# [Product] vs. [Alternative] — Which fits [Use case]?

| Criterion | [Product] | [Alt A] | [Alt B] | Source |
|-----------|-----------|---------|---------|--------|
| [Feature] | [value]   | [value] | [value] | [link] |

Fit Statements:
1. **[Product]** suits [Use case] when [Condition].
2. **[Alt A]** fits [Use case] when [Condition].

Schema: Article. Author + last updated.
```

### Template 4: Use Case / Industry Page
**Goal**: Connect product to outcomes in context readers recognize.

```markdown
# [Industry/Use Case] — [Outcome KPI]
**Teams reduce [Metric] by [Y%] in [Timeframe].**

## Mini Case Study
[Company] used [Feature] to [Action], resulting in [Metric] within [Timeframe].

## How It Works
### [Feature 1] — [Feature → How → Outcome + triples]

## Who Uses This
Roles: [Role 1], [Role 2] | Integrations: [Integration 1], [Integration 2]

Schema: Article. Author + last updated.
```

---

## Content Cluster Architecture

**Hub + Spoke model**:
- Hub page: Broad category ("What is X?") — high authority, links to all spokes
- Spoke pages: Specific sub-topics, use cases, comparisons — link back to hub
- Supporting pages: Blog posts, case studies — link to both hub and spokes

Every cluster page should reference the same core semantic triples to build consensus.

---

## Technical AEO Checklist

- [ ] Schema markup on every page (Article, FAQ, Product as applicable)
- [ ] Author byline with credentials
- [ ] Last updated date visible
- [ ] Canonical URLs set
- [ ] Open Graph tags (for LLM training data crawlers)
- [ ] FAQ section on every major page (2–5 Q&As minimum)
- [ ] Internal links from hub → spokes → hub
- [ ] External links to credible sources (builds trust signal)
- [ ] Page load <2s (fast pages get crawled more)
- [ ] Mobile responsive (AI crawlers check mobile-first)

---

## Monitoring AEO Performance

**Manual checks**: Search your target queries in ChatGPT, Perplexity, Claude. Note if/how you're cited.

**Metrics to track**:
- Brand mention frequency in AI responses (manual sampling, monthly)
- Organic search impressions (Google Search Console) — AEO often improves these too
- Direct traffic uplift (attributed to AI visibility)
- Share of voice vs. competitors in AI answers
