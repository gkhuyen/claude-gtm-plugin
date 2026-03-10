---
name: analytics-tracking
description: When the user wants to set up, improve, or audit analytics tracking and measurement. Also use when the user mentions "set up tracking," "GA4," "Google Analytics," "conversion tracking," "event tracking," "UTM parameters," "tag manager," "GTM," "analytics implementation," or "tracking plan." For A/B test measurement, see ab-test-setup.
---

# Analytics Tracking

Expert analytics implementation across GA4, GTM, Mixpanel, Amplitude, and Segment.

**Principles**:
- Track for decisions, not data — every event should inform an action
- Start with the questions, work backwards to what you need to track
- Consistent naming conventions before implementation
- Quality > quantity

---

## Initial Assessment

Before implementing, understand:
1. What decisions will this data inform?
2. What's the current tracking state and toolstack?
3. What are the key conversion actions?
4. Any privacy/compliance requirements (GDPR, CCPA)?

---

## Event Naming Convention

**Recommended format**: `object_action` in lowercase snake_case

```
signup_completed | cta_hero_clicked | checkout_started | onboarding_step_completed
```

Rules: specific over vague (`cta_hero_clicked` not `button_clicked`), past tense for completed actions, context in properties (not event name), no spaces or special characters.

---

## Tracking Plan

Every event should be documented with:

```
Event Name | Category | Properties | Trigger | Notes
```

### Marketing Site Events

| Event | Key Properties |
|-------|---------------|
| `page_view` | page_title, page_location, referrer |
| `cta_clicked` | button_text, location, page |
| `form_submitted` | form_type, page |
| `resource_downloaded` | resource_name, type |
| `video_played` | video_id, title |
| `scroll_depth` | percent (25/50/75/100) |
| `signup_started` | source, medium |
| `signup_completed` | method, plan |
| `demo_requested` | page |

### Product / App Events

| Event | Key Properties |
|-------|---------------|
| `onboarding_step_completed` | step_number, step_name |
| `onboarding_completed` | duration_seconds, steps_skipped |
| `feature_used` | feature_name, context |
| `trial_started` | plan, source |
| `pricing_viewed` | current_plan |
| `checkout_started` | plan, billing_period |
| `purchase_completed` | plan, value, currency |
| `subscription_cancelled` | plan, reason |

### E-commerce Events

| Event | Key Properties |
|-------|---------------|
| `product_viewed` | product_id, category, price |
| `product_added_to_cart` | product_id, price, quantity |
| `checkout_started` | cart_value, items_count |
| `purchase_completed` | order_id, value, products[ ] |

---

## Standard Event Properties

Always include these where relevant:

**User context**: `user_id`, `user_type` (free/paid/admin), `account_id`, `plan_type`

**Attribution**: `source`, `medium`, `campaign`, `content`, `term` (UTM params)

**Page**: `page_title`, `page_location`, `content_group`

**Timing**: `timestamp`, `session_duration`

Avoid PII in event properties. Don't duplicate GA4 automatic properties.

---

## GA4 Implementation

### Setup

```javascript
// gtag.js — custom event
gtag('event', 'signup_completed', {
  'method': 'email',
  'plan': 'free',
  'user_id': userId
});

// GTM dataLayer
dataLayer.push({
  'event': 'signup_completed',
  'method': 'email',
  'plan': 'free'
});
```

**Enhanced Measurement** (enable in GA4): page_view, scroll (90%), outbound_click, site_search, video_engagement, file_download.

**Conversions**: Admin → Events → Toggle "Mark as conversion". Set counting: once per session (form submit) or every time (purchase).

**Custom Dimensions**: Admin → Custom definitions → set scope (Event/User/Item). Parameter name must match exactly.

### GA4 Reporting Essentials

- **Funnel Exploration**: Map signup → activation → purchase → retention
- **Cohort Analysis**: Compare retention by acquisition date/channel
- **Path Exploration**: See actual user journeys through your product
- **Segment Comparisons**: Paid vs. organic, mobile vs. desktop, free vs. paid users

---

## Google Tag Manager (GTM)

**Container structure**:
- Tags: GA4 Configuration (base) + GA4 Event tags
- Triggers: pageview, custom event, click, form submission
- Variables: dataLayer variables, built-in (Page URL, Click Text), lookup tables

**Testing**: Preview mode before publishing. Check Tag Assistant shows events firing with correct properties.

**Best practices**: One GA4 Config tag. Use dataLayer pushes from app code, capture in GTM tags. Version control with meaningful publish notes.

---

## UTM Parameters

Convention: `utm_source={channel}&utm_medium={cpc|email|organic|social}&utm_campaign={id}&utm_content={variant}&utm_term={keyword}`

**Rules**:
- Apply to ALL paid and email links
- Never use on internal links (breaks session attribution)
- Consistent naming: use lowercase, hyphens not spaces
- Document in a UTM tracking sheet

---

## Multi-Tool Setups

**GA4 + Mixpanel/Amplitude**: Use Segment as CDP to send events once, route to multiple tools. Define schema in Segment, map properties per destination.

**Server-side tracking**: Use GA4 Measurement Protocol for backend events (purchases, subscriptions). Reduces ad blocker impact.

---

## Validation & QA

**Before launch**:
- [ ] Events fire in GA4 DebugView
- [ ] Properties have expected values
- [ ] No duplicate events
- [ ] Conversions marked correctly
- [ ] UTM parameters captured on landing

**Ongoing monitoring**:
- Weekly: Check for sudden drops in key events (>20% change = investigate)
- Monthly: Audit for new pages/features without tracking
- Quarterly: Full tracking plan review — remove stale events, add missing ones

---

## Privacy & Compliance

**GDPR/CCPA**: Implement consent management (OneTrust, Cookiebot). Block GA4 until consent granted. Use IP anonymization (`anonymize_ip: true`).

**GA4 data retention**: Set to 14 months max (Admin → Data Settings). Enable Google Signals only if needed.

**PII hygiene**: Never send email, name, or phone as event properties. Use hashed user IDs only.
