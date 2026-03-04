# GTM Skills — Claude Code Plugin

A comprehensive Go-to-Market plugin for Claude Code. It gives Claude deep GTM expertise across 160+ skills covering SEO, content, copywriting, outbound sales, social media, analytics, product strategy, and more — plus a `/bootstrap` command that sets up a project with the context Claude needs to work in your voice, for your brand.

## Installation

Install via the Claude Code plugin registry or by cloning this repo and loading it locally.

## Getting Started

Run `/bootstrap` in any new project directory to kick things off.

```
/bootstrap
```

This launches an agency-style onboarding interview. Claude will ask about your brand, your audience, your voice, and your goals — then generate four foundational files in your working directory:

| File | Purpose |
|---|---|
| `CLAUDE.md` | Instructions for Claude: how to use the other files, routing rules for new learnings |
| `BRAND.md` | Brand guidelines — positioning, messaging, audience, competitors, brand voice |
| `SOUL.md` | Personal guidelines — your individual voice, writing style, and personality |
| `MEMORY.md` | Operational log — what's happened, what's working, what isn't (append-only) |

Once these files exist, Claude will read the relevant ones before every task — and will know where to route anything new it learns about you or your brand.

## How the Four Files Work

**`BRAND.md`** is about the brand as an entity: what it is, what it stands for, how it's positioned in the market, and how the brand communicates. Update this when anything about the brand changes.

**`SOUL.md`** is about you as a person: how you naturally write, think, and communicate — your quirks, references, and voice. This is separate from the brand because you may sound different personally than the brand does officially.

**`MEMORY.md`** is a living log, not a preferences file. It records what actually happened — campaigns launched, results, decisions made, observations, open questions. Entries are always appended with a date and never overwritten.

**`CLAUDE.md`** tells Claude how to behave in this project: which files to read before which tasks, and where to route new information as work progresses.

## Skills

The plugin includes 160+ GTM skills organized by domain:

**SEO & Search**
`seo` · `seo-audit` · `seo-geo` · `keyword-research` · `keyword-expansion` · `programmatic-seo` · `backlink-analyzer` · `seo-backlink-strategy` · `serp-analysis` · `seo-optimizer`

**AI Search & GEO**
`aeo-optimization` · `aeo-scorecard` · `geo-aeo-optimization` · `ai-search-optimization` · `project-aeo-monitoring-tools`

**Content & Copywriting**
`content-strategy` · `content-marketing` · `content-research` · `content-marketer` · `copywriting` · `blog-writer` · `blog-writing` · `blog-post-writer` · `technical-blog-writing` · `content-brief` · `content-optimizer`

**Social Media**
`social-media` · `social-content` · `linkedin` · `linkedin-content` · `linkedin-personal-branding` · `linkedin-post-optimizer` · `twitter-x` · `youtube` · `ai-social-media-content` · `social-repurposer`

**Email & Outbound**
`cold_email` · `cold-email-sequence-generator` · `cold-outreach-generator` · `email-sequence` · `email-template-generator` · `outbound-sequences` · `outbound-plays` · `outbound-optimizer` · `gtm-outbound` · `bd-email`

**Growth & Product**
`growth` · `growth-strategy` · `growth-loops` · `product-market-fit` · `launch-gtm-execution` · `launch-marketing` · `product-hunt-launch` · `lead-generation` · `lead-magnet` · `referral-program` · `funnel-analysis`

**Sales**
`founder-sales` · `enterprise-sales` · `sales-qualification` · `product-led-sales` · `building-sales-team` · `startup-icp-definer`

**Analytics & Research**
`analytics-tracking` · `analytics-interpretation` · `competitor-analysis` · `competitor-teardown` · `market-researcher` · `market-research-reports` · `posthog-analytics` · `google-analytics`

**Strategy & Positioning**
`positioning-messaging` · `brand-messaging-architecture` · `pricing-strategy` · `product-strategy` · `startup-go-to-market` · `Go-to-Market-Planner` · `storybrand-messaging`

**Ads & Paid**
`paid-ads` · `ad-copy-generator` · `landing-page` · `landing-page-copywriter` · `cro-methodology`

**CRM & Automation**
`hubspot-crm` · `intercom-crm` · `espocrm-development` · `crm-integration` · `marketing-automation`

## Commands

| Command | Description |
|---|---|
| `/bootstrap` | Onboard a new project — interview-style setup generating CLAUDE.md, BRAND.md, SOUL.md, and MEMORY.md |

## Routing Rules

As work progresses, Claude routes new information to the right file automatically:

- New brand info (positioning, messaging, audience insights) → `BRAND.md`
- New personal info (writing preferences, quirks, reference examples) → `SOUL.md`
- Operational progress (what launched, what worked, decisions made) → `MEMORY.md` (appended, dated)
