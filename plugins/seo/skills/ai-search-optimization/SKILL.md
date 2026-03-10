---
name: ai-search-optimization
description: >-
  Answer Engine Optimization (AEO) and Generative Engine Optimization (GEO) strategies for
  AI-powered search visibility in ChatGPT, Perplexity, Google AI Overviews, and other AI
  search platforms. Use when working with aeo, geo, ai search, chatgpt search, perplexity,
  ai overviews, generative search, llm visibility.
metadata:
  version: "1.0.0"
---

# AI Search Optimization (AEO & GEO)

Optimizing content for visibility in ChatGPT, Perplexity, Google AI Overviews, Microsoft Copilot, and other generative AI platforms.

## 1. AEO vs GEO vs Traditional SEO

| Aspect | Traditional SEO | AEO/GEO |
|--------|----------------|---------|
| Goal | Rank in SERPs | Be cited in AI answers |
| User behavior | Click through to site | Get answer directly |
| Content format | Keyword-optimized pages | Structured, citable content |
| Success metric | Click-through rate | Citation frequency |
| Query type | Short keywords | Conversational, long-tail |

**2025 landscape:** Google AI Overviews has 2B+ monthly users; ~60% of searches end without a click. Optimize for citation, not just ranking.

---

## 2. Content Structure for AI Readability

### Inverted Pyramid Pattern

```
┌──────────────────────────────────┐
│  DIRECT ANSWER (1-2 sentences)   │ ← AI extracts this first
├──────────────────────────────────┤
│  KEY FACTS & CONTEXT             │ ← Supporting bullets/data
├──────────────────────────────────┤
│  DETAILED EXPLANATION            │ ← Background, examples
├──────────────────────────────────┤
│  RELATED TOPICS                  │ ← Authority signals
└──────────────────────────────────┘
```

### Semantic HTML Structure

```html
<article>
  <header>
    <h1>Primary Topic as Question or Clear Statement</h1>
    <p class="summary">Direct 2-3 sentence answer to the main question.</p>
  </header>
  <main>
    <section>
      <h2>Subtopic Heading</h2>
      <p>Detailed explanation with facts and data.</p>
      <ul>
        <li>Key point with specific information</li>
      </ul>
    </section>
  </main>
  <aside>
    <dl><dt>Term</dt><dd>Definition</dd></dl>
  </aside>
</article>
```

**Rules:** Single H1 per page. Use question-format headings. AI prefers tables, ordered lists, and definition lists for extraction.

---

## 3. Schema Markup for AI Visibility

Schema significantly improves citation rates:
- FAQPage schema: **2.5x** rise in answer inclusion
- Article schema with author: **2.2x** boost in citations
- Organization schema: **2.8x** increase in citation frequency
- Pages with 15+ schema types: **2.4x** higher citation rates

### FAQPage Schema

```json
{
  "@context": "https://schema.org",
  "@type": "FAQPage",
  "mainEntity": [{
    "@type": "Question",
    "name": "What is Answer Engine Optimization?",
    "acceptedAnswer": {
      "@type": "Answer",
      "text": "AEO is a strategic approach to structuring content so AI platforms like ChatGPT, Perplexity, and Google AI Overviews can easily extract and cite it as direct answers."
    }
  }]
}
```

### HowTo Schema

```json
{
  "@context": "https://schema.org",
  "@type": "HowTo",
  "name": "How to Optimize Content for AI Search",
  "step": [
    { "@type": "HowToStep", "position": 1, "name": "Structure Content Semantically", "text": "Use HTML5 semantic elements: article, section, aside" },
    { "@type": "HowToStep", "position": 2, "name": "Implement Schema Markup", "text": "Add FAQPage, HowTo, and Article schema" },
    { "@type": "HowToStep", "position": 3, "name": "Optimize for Conversational Queries", "text": "Answer natural language questions directly" }
  ]
}
```

### Article Schema (with Author — critical for E-E-A-T)

```json
{
  "@context": "https://schema.org",
  "@type": "Article",
  "headline": "Complete Guide to AI Search Optimization",
  "datePublished": "2025-01-15",
  "dateModified": "2025-01-15",
  "author": {
    "@type": "Person",
    "name": "Expert Name",
    "url": "https://example.com/about/expert-name",
    "jobTitle": "SEO Specialist",
    "sameAs": ["https://linkedin.com/in/expertname"]
  },
  "publisher": {
    "@type": "Organization",
    "name": "Company Name",
    "logo": { "@type": "ImageObject", "url": "https://example.com/logo.png" }
  }
}
```

---

## 4. Content Writing for AI Citation

### Conversational Query Optimization

Write content that answers natural language questions directly:

| Avoid | Prefer |
|-------|--------|
| "This article explains SEO..." | "AEO differs from SEO in three key ways..." |
| Long wind-up paragraphs | Answer in first sentence, explain after |
| Vague claims | Specific facts, data, stats with sources |
| Dense walls of text | Short paragraphs + structured lists |

### Direct Answer Templates

```markdown
# What is [Topic]?

[Topic] is [definition in one clear sentence]. [Key characteristic or differentiator].

**Key facts:**
- [Fact 1 with data]
- [Fact 2 with data]
- [Fact 3 with data]

## How [Topic] works

[Step-by-step or mechanism explanation]

## [Topic] vs [Alternative]

| Aspect | [Topic] | [Alternative] |
|--------|---------|---------------|
| [Row 1] | ... | ... |
```

### E-E-A-T Signals for AI Trust

AI engines prioritize content with demonstrated expertise:

- **Experience**: First-person accounts, case studies, specific examples
- **Expertise**: Author credentials, clear bio with credentials link
- **Authoritativeness**: Citations from recognized sources, industry data
- **Trustworthiness**: Accurate facts, updated dates, transparent methodology

---

## 5. Technical AEO Requirements

### Crawlability Checklist

- [ ] XML sitemap submitted; pages indexed in Search Console
- [ ] `robots.txt` allows AI crawlers (Googlebot, GPTBot, PerplexityBot)
- [ ] HTTPS enabled; page speed > 90 mobile (PageSpeed Insights)
- [ ] Core Web Vitals passing (LCP < 2.5s, CLS < 0.1, INP < 200ms)
- [ ] Canonical tags on all pages
- [ ] Structured data validated (Schema Markup Validator)

### Allow AI Crawlers

```
# robots.txt — allow major AI crawlers
User-agent: GPTBot
Allow: /

User-agent: PerplexityBot
Allow: /

User-agent: ClaudeBot
Allow: /

User-agent: Googlebot
Allow: /
```

### Content Freshness

AI engines heavily weight recency:
- Add `dateModified` to all Article schema
- Include "Last updated: [date]" visible on page
- Refresh statistics and examples quarterly
- Monitor Search Console for ranking drops

---

## 6. Platform-Specific Optimization

### Google AI Overviews

- Target featured snippet formats: numbered lists, tables, direct definitions
- Use FAQ schema on informational pages
- Aim for content in top 5 organic positions (AI Overviews strongly favor these)
- Include question-format H2s matching common queries

### Perplexity AI

- Prioritize recency: update content regularly
- Cite authoritative sources inline (Perplexity shows citations)
- Use clear factual statements AI can quote directly
- Structured data and clean semantic HTML improve inclusion

### ChatGPT Search

- Ensure pages are crawlable by GPTBot
- Long-form comprehensive coverage improves authority
- Include statistics with source citations
- Named entities (people, companies, products) improve recognition

---

## 7. AEO Audit Checklist

### Content Audit

- [ ] Does each page answer a clear question in the first paragraph?
- [ ] Are headings phrased as questions users actually ask?
- [ ] Is data cited with sources and dates?
- [ ] Does content use tables/lists for structured information?
- [ ] Is author expertise clearly shown (bio, credentials, links)?

### Technical Audit

- [ ] FAQPage schema on FAQ/support pages
- [ ] Article schema with author on blog/guide pages
- [ ] HowTo schema on instructional pages
- [ ] Organization schema on homepage
- [ ] Breadcrumb schema on all pages
- [ ] AI crawlers allowed in robots.txt
- [ ] `dateModified` updated on revised content

### Measurement

Track monthly via Search Console + manual spot-checks:
- Impressions in AI Overview placements
- Citation frequency in Perplexity (search brand/product)
- Featured snippet wins (proxy for AI citation eligibility)
- Zero-click rate trends (rising = more AI overview exposure)
