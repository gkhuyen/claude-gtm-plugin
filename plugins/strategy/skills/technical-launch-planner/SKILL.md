---
name: technical-launch-planner
description: Plan and execute technical product launches for developer tools, APIs, and technical products. Use this skill when technical PMMs need to "plan a launch", "create a launch strategy", "coordinate a product release", or "prepare for GA/beta launch".
---

# Technical Launch Planner

## Overview

Plan and execute launches for developer tools, APIs, SDKs, technical infrastructure, B2D products, and SaaS with technical buyers.

**Quick start:**
```bash
scripts/assess_launch_tier.sh    # Determine tier (1/2/3)
scripts/generate_launch_plan.sh  # Create full plan
scripts/validate_readiness.sh    # Pre-launch readiness check
```

---

## Launch Tiers

| Tier | Type | Examples | Timeline | Investment |
|------|------|----------|----------|------------|
| **1 — Major** | New product/GA, major version, platform expansion | Full GTM, PR, events, paid | 12-16 weeks | High |
| **2 — Standard** | New features, integrations, SDKs, regional expansion | Blog, docs, email, social | 6-8 weeks | Medium |
| **3 — Minor** | Updates, patches, small features | Changelog, in-app, release notes | 2-4 weeks | Low |

See `references/launch_tiers.md` for complete framework.

---

## Launch Planning Workflow

### Phase 1: Planning (T-12 to T-8 weeks)
1. Run `scripts/assess_launch_tier.sh`
2. Stakeholder kickoff: Product/Engineering, DevRel, Sales Engineering, Marketing/Comms, Partners
3. Define success metrics: API sign-ups, SDK downloads, DAD/WAD, "hello world" completions, doc traffic
4. Run `scripts/generate_launch_plan.sh` to create timeline

### Phase 2: Build (T-8 to T-4 weeks)

**Documentation:**
- [ ] Getting started guide
- [ ] API reference
- [ ] Integration guides
- [ ] Migration guide (if applicable)
- [ ] Troubleshooting FAQ

**Code assets:**
- [ ] SDKs built and tested
- [ ] Sample apps and code snippets
- [ ] Sandbox/playground environment

**Marketing assets:**
- [ ] Technical blog post
- [ ] Demo video
- [ ] Announcement email
- [ ] Social media plan
- [ ] Press release (Tier 1 only)

**Sales enablement:**
- [ ] Technical battlecard, demo script, FAQ/objections, pricing materials, competitive positioning

### Phase 3: Prepare (T-4 to T-1 weeks)
- [ ] Internal: sales training, support training, partner briefings, demo day
- [ ] External: beta customers briefed, developer advocates prepared, community moderators ready
- [ ] Run `scripts/validate_readiness.sh`
- [ ] All docs on staging, SDKs tagged, demo environment tested, monitoring configured, escalation path defined

### Phase 4: Launch Day

**9 AM:** Publish docs, release SDKs, deploy blog post, send announcement email, post social, update website

**12 PM:** Monitor metrics dashboard, respond to community, share to external communities (HN, Reddit, Discord)

**3 PM:** HN/Reddit posts (Tier 1), developer advocate content, partner announcements

**EOD:** Day 1 metrics report, team debrief, issue triage

### Phase 5: Post-Launch (T+1 to T+4 weeks)

**Week 1:** Daily metrics, community Q&A, bug triage, feedback synthesis

**Week 2:** First adoption metrics, customer interviews, doc updates, follow-up content

**Week 4:** Launch retrospective, success metrics report, lessons learned, update playbook

---

## Developer-First Best Practices

**1. Documentation is non-negotiable.** Launch is NOT ready without: getting started guide, API reference, 3+ code samples, integration guide. "If it's not documented, it doesn't exist."

**2. Show, don't tell.**
```python
# Good: actual code
client = acme_sdk.Client(api_key="your_key")
result = client.widgets.create(name="My Widget")
```
Bad: "Our SDK makes it easy to create widgets with just a few lines of code."

**3. Interactive > passive.** Priority: interactive playground > live demo > demo video > static screenshots.

**4. Honest technical communication.** State limitations clearly, include performance metrics, show migration complexity, disclose breaking changes. Developers hate overpromising and hidden limitations.

**5. Community-first.** Answer Stack Overflow, engage GitHub discussions, respond on Hacker News, join Discord/Slack. Don't spam, don't ignore negative feedback, don't only show up for launches.

---

## Channels for Developers

**Primary:** Developer docs, GitHub/GitLab, developer blog, API changelog, release notes

**Secondary:** Dev.to, Hacker News, Reddit, Technical Twitter/X, Discord/Slack communities, YouTube tutorials, developer newsletters

**Tertiary:** Webinars/workshops, conferences, podcasts, case studies

---

## Developer Adoption Metrics

**Activation:** Sandbox sign-ups, first API call within 24h, SDK downloads, hello-world completions

**Engagement:** Daily/Weekly Active Developers, API calls per developer, features adopted, integration depth

**Retention:** Day 7/30/90 retention, churn rate, Developer NPS

See `references/metrics_frameworks.md` for complete guide.

---

## Templates

### Technical Blog Post
```markdown
# Introducing [Feature/Product]
## The Problem
[Developer pain point in technical detail]
## The Solution
[High-level technical overview with architecture diagram]
## Getting Started
[Code sample showing basic usage]
## What's Next
[Roadmap tease + link to full documentation]
```

### Launch Email
```
Subject: [Feature] is now available

What it does: [One sentence technical description]
Why it matters: [Developer benefit]
Get started in 5 minutes: [Code snippet or quick start link]

Resources: Documentation | Sample code | API reference
Questions? Reply or join us in [Discord/Slack].
```

### Changelog Entry
```markdown
## [Version] - YYYY-MM-DD
### Added
- [Feature]: [Technical description] — Example: `client.newMethod(params)` — [Docs link]
### Changed
- [Breaking change]: [What changed and why] — Migration guide: [link]
### Fixed / Deprecated
```

---

## Partner/Integration Launches

When launching with partners:
- [ ] Joint messaging and co-marketing plan agreed
- [ ] Technical integration tested end-to-end
- [ ] Mutual customer references secured
- [ ] Co-branded assets, joint case study, partner doc
- [ ] Sales team training completed

Launch activities: co-authored blog post, joint webinar, cross-promotion on social, email to both lists, mutual press release (Tier 1).

---

## Common Pitfalls

| Pitfall | Solution |
|---------|----------|
| Launching without complete docs | Docs are non-negotiable — delay launch if needed |
| Marketing-speak ("revolutionary", "seamless") | Use concrete technical language, metrics, and code |
| Breaking changes with no migration guide | Provide migration guide, migration tools, version support plan |
| All effort on Day 1, nothing after | Plan a 4-week post-launch content calendar |
| Launch and disappear | Active community engagement, regular office hours |

---

## Launch Retrospective (Within 30 Days)

- Did we hit adoption targets? Day 1 / Week 1 / Month 1 usage?
- Developer sentiment (NPS, social, support tickets)?
- Which channels drove most adoption? Which content resonated?
- Where did developers get stuck? What docs were missing?
- Action items: doc improvements, messaging refinements, process updates

---

## Resources

- `references/launch_tiers.md` — complete tier framework
- `references/developer_enablement.md` — developer enablement checklist
- `references/launch_messaging.md` — technical messaging templates
- `references/metrics_frameworks.md` — developer product metrics guide
