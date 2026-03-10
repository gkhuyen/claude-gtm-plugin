---
name: retain
description: Use this skill when working on retention, re-engagement, or churn prevention. Covers retention analysis frameworks, re-engagement trigger design, gamification, habit formation, and loyalty programs.
---

# Retain

Behavioral strategist that designs systems to keep users engaged and coming back.

**Philosophy**: Retention is a byproduct of value. Habits beat features. Early intervention beats win-back. Never use dark patterns — make cancellation easy.

---

## Framework: Understand → Engage → Reward

| Phase | Goal | Deliverables |
|-------|------|--------------|
| **Understand** | Know why users churn | Cohort analysis, churn predictors, health scores |
| **Engage** | Bring users back | Re-engagement campaigns, triggers, habit formation |
| **Reward** | Make loyalty worthwhile | Gamification, loyalty programs, streak systems |

---

## Retention Analysis

### Cohort Retention

Track cohorts by signup week/month. Look for:
- Where does retention curve flatten? (natural retention floor)
- Which cohorts retain better? (source, onboarding path, feature adoption)
- At what day/week does most churn happen?

### Churn Risk Scoring

| Level | Score | Action |
|-------|-------|--------|
| Low | 0–29 | Continue normal engagement |
| Medium | 30–49 | Automated re-engagement campaign |
| High | 50–69 | Personalized intervention |
| Critical | 70+ | Human outreach (call / 1:1 email) |

### Customer Health Score (100 points)

| Dimension | Weight | Signals |
|-----------|--------|---------|
| Usage frequency | 25% | DAU/MAU ratio, sessions, last login |
| Feature depth | 20% | Feature adoption %, core feature use |
| Engagement | 20% | Time on app, actions per session |
| Satisfaction | 15% | NPS, CSAT, support sentiment |
| Growth | 10% | Seat additions, plan upgrades |
| Relationship | 10% | Community participation, referrals |

**Thresholds**: 80+ = Healthy (upsell) | 60–79 = Stable (monitor) | 40–59 = At Risk (automate) | 0–39 = Critical (human touch).

---

## Re-engagement Triggers

| Trigger | Condition | Channel | Max Frequency |
|---------|-----------|---------|---------------|
| Early dormancy | 3–7 days inactive | Push | 4×/month |
| Mid dormancy | 7–14 days inactive | Email | 2×/month |
| Onboarding drop | Incomplete onboarding | Email | 3×/month |
| Feature discovery | Unused high-value feature | In-app | 1×/month |
| Streak at risk | Streak expires in 6 hours | Push | As needed |

---

## Habit Formation (Hook Model)

| Phase | Goal | Examples |
|-------|------|----------|
| **Trigger** | Create the cue | Push notifications, email digest, internal motivation |
| **Action** | Minimum viable behavior | One-click action, simple daily task |
| **Variable Reward** | Unpredictable value | Social recognition, progress unlocks, surprise content |
| **Investment** | User commits something | Profile data, custom settings, social connections |

**Streak system**: 7-day → weekly badge | 30-day → monthly badge | 100-day → century badge | 365-day → yearly badge.

---

## Gamification Elements

**Badge rarity**: Common (first action, 7-day streak) → Rare (30-day streak, all features used) → Epic (community helper) → Legendary (beta user / founder).

**Progress levels**: 5 levels with XP ranges. Benefits escalate: custom themes → priority support → beta access → community status.

**Leaderboards**: Weekly or monthly. Show "nearby" positions (not just top 10) to motivate mid-tier users.

---

## Subscription Retention (Cancellation Funnel)

| Step | Option | Expected Save Rate |
|------|--------|-------------------|
| 1 | Choose cancellation reason | 0% (required) |
| 2 | Offer pause (up to 3 months) | 20–25% |
| 3 | Offer downgrade | 15–20% |
| 4 | Offer 30% discount for 3 months | 10–15% |
| 5 | Confirm cancellation + collect feedback | — |

**Save offer by reason**:
- Too expensive → 30% off for 3 months
- Budget cut → downgrade to lower plan
- Not using → free training session
- Temporary need → pause subscription
- Competitor → 40% off for 6 months

---

## Onboarding Optimization

**Activation milestones** (impact on Day 30 retention):

| Milestone | Target Time | D30 Retention Impact |
|-----------|-------------|---------------------|
| Account created | T+0 | Baseline |
| Profile complete | T+5 min | +8% |
| First core action | T+24 hr | +15% |
| First value experience | T+3 days | +25% |
| 3-day active streak | T+7 days | +35% |
| 2+ sessions/week | T+14 days | +45% |

**Progressive disclosure**: Week 1 = core features only | Week 2 = intermediate features + tooltips | Week 3 = advanced features + walkthroughs | Week 4+ = full access.

---

## Principles

**Always**: Base strategies on data. Test before full rollout. Respect opt-out preferences. Balance short-term engagement with long-term value.

**Never**: Use dark patterns. Spam notifications. Make cancellation difficult. Prioritize metrics over user value. Ignore early churn signals.
