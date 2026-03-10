---
name: posthog-analytics
description: Use this skill when implementing PostHog analytics, event tracking, feature flags, or dashboards
---

# PostHog Analytics

Product analytics with PostHog — event tracking, user identification, feature flags, and dashboards.

**Principle**: Measure what matters, not everything. Track what informs decisions about activation, retention, and feature adoption.

---

## Installation

### Next.js (App Router)

```bash
npm install posthog-js
```

```typescript
// lib/posthog.ts
import posthog from 'posthog-js';

export function initPostHog() {
  if (typeof window !== 'undefined' && !posthog.__loaded) {
    posthog.init(process.env.NEXT_PUBLIC_POSTHOG_KEY!, {
      api_host: process.env.NEXT_PUBLIC_POSTHOG_HOST || 'https://us.i.posthog.com',
      person_profiles: 'identified_only',
      capture_pageview: false, // handle manually for SPA
      capture_pageleave: true,
    });
  }
  return posthog;
}

export { posthog };
```

```typescript
// app/providers.tsx — wraps layout, tracks pageviews
'use client';
import { useEffect } from 'react';
import { usePathname, useSearchParams } from 'next/navigation';
import { initPostHog, posthog } from '@/lib/posthog';

export function PostHogProvider({ children }: { children: React.ReactNode }) {
  const pathname = usePathname();
  const searchParams = useSearchParams();

  useEffect(() => { initPostHog(); }, []);

  useEffect(() => {
    if (pathname) {
      const url = window.origin + pathname + (searchParams.toString() ? `?${searchParams}` : '');
      posthog.capture('$pageview', { $current_url: url });
    }
  }, [pathname, searchParams]);

  return <>{children}</>;
}
```

### React (Vite)

```typescript
import posthog from 'posthog-js';
import { PostHogProvider } from 'posthog-js/react';

posthog.init(import.meta.env.VITE_POSTHOG_KEY, {
  api_host: 'https://us.i.posthog.com',
  person_profiles: 'identified_only',
});

// Wrap app: <PostHogProvider client={posthog}><App /></PostHogProvider>
```

### Python (Backend)

```python
import posthog, os

posthog.project_api_key = os.environ["POSTHOG_API_KEY"]
posthog.host = os.environ.get("POSTHOG_HOST", "https://us.i.posthog.com")

posthog.capture(distinct_id=user_id, event="feature_used", properties={"feature": "export"})
posthog.identify(user_id, {"email": email, "plan": "pro"})
```

### Node.js (Backend)

```typescript
import { PostHog } from 'posthog-node';

const posthog = new PostHog(process.env.POSTHOG_API_KEY!, {
  host: 'https://us.i.posthog.com',
});
process.on('SIGTERM', () => posthog.shutdown());

posthog.capture({ distinctId: userId, event: 'feature_used', properties: { feature: 'export' } });
```

---

## Environment Variables

```bash
NEXT_PUBLIC_POSTHOG_KEY=phc_xxxx   # frontend (safe to expose)
NEXT_PUBLIC_POSTHOG_HOST=https://us.i.posthog.com
POSTHOG_API_KEY=phc_xxxx           # backend (keep private)
```

---

## User Identification

```typescript
// On signup
posthog.identify(user.id, { email, name, plan: 'free', created_at: new Date().toISOString() });
posthog.capture('user_signed_up', { signup_method: 'email' });

// On login
posthog.identify(user.id, { email, plan, last_login: new Date().toISOString() });

// On logout
posthog.capture('user_logged_out');
posthog.reset(); // clears identity
```

---

## Event Naming Convention

Use `object_action` in snake_case, past tense:

```typescript
// ✅ Good
'user_signed_up' | 'feature_created' | 'subscription_upgraded' | 'onboarding_completed'

// ❌ Bad
'click' | 'ButtonClick' | 'user signup' | 'creatingFeature'
```

## Core Events

```typescript
// Auth
posthog.capture('user_signed_up', { signup_method: 'google' | 'email', referral_source: 'organic' });
posthog.capture('user_logged_in', { login_method: 'email' });

// Onboarding
posthog.capture('onboarding_step_completed', { step_name: 'profile', step_number: 1, total_steps: 3 });
posthog.capture('onboarding_completed', { duration_seconds: 120 });
posthog.capture('onboarding_skipped', { skipped_at_step: 2 });

// Features
posthog.capture('feature_used', { feature_name: 'export', context: 'dashboard' });
posthog.capture('project_created', { template_used: 'blank' });

// Billing
posthog.capture('checkout_started', { plan: 'pro', billing_period: 'annual', price: 29 });
posthog.capture('subscription_upgraded', { from_plan: 'free', to_plan: 'pro', mrr_change: 29 });
posthog.capture('subscription_cancelled', { plan: 'pro', reason: 'too_expensive' });

// Errors
posthog.capture('error_occurred', { error_type: 'api_error', error_message: '...', page: '/dashboard' });
```

## React Hook

```typescript
// hooks/useTrack.ts
import { useCallback } from 'react';
import { posthog } from '@/lib/posthog';

export function useTrack() {
  const track = useCallback((event: string, properties?: Record<string, unknown>) => {
    posthog.capture(event, properties);
  }, []);
  return { track };
}
```

---

## Feature Flags

```typescript
// Client-side
import { useFeatureFlagEnabled, useFeatureFlagPayload } from 'posthog-js/react';

function Component() {
  const enabled = useFeatureFlagEnabled('new-dashboard-ui');
  const config = useFeatureFlagPayload('experiment-cta') as { text: string };
  return enabled ? <NewUI ctaText={config?.text} /> : <OldUI />;
}

// Server-side (Node)
const isEnabled = await posthog.isFeatureEnabled('new-feature', userId);
```

---

## Dashboards & Funnels

**Activation funnel** — create in PostHog → Funnels:
1. `user_signed_up`
2. `onboarding_completed`
3. First core action (e.g., `project_created`)
4. Return visit within 7 days

**Retention** — PostHog → Retention: starting event `user_signed_up`, returning event `user_logged_in`, weekly cohorts.

**Key dashboards to build**:
- Activation: signup → first value, time-to-activate, onboarding completion rate
- Engagement: DAU/WAU/MAU, feature usage heatmap, most-used features
- Revenue: plan distribution, upgrade/downgrade funnel, cancellation reasons
- Errors: error rate by page, most common error types

---

## Best Practices

- Track the minimum needed to answer your key product questions
- Always include `user_id` and `plan` as super properties for easy segmentation
- Test tracking in development with `posthog.debug()` before shipping
- Use feature flags for all new features — enables safe rollouts and A/B tests
- Set up alerts in PostHog for sudden drops in key events (>20% change)
