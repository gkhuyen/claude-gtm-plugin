---
name: landing-page-guide-v2
description: Use this skill when creating distinctive, high-converting landing pages that combine proven conversion elements with exceptional design quality. Build beautiful, memorable landing pages using Next.js 14+ and ShadCN UI that avoid generic AI aesthetics while following the 11 essential elements framework.
---

# Landing Page Guide V2

Creates **distinctive, high-converting landing pages** combining proven conversion structure with exceptional design — using Next.js 14+, TypeScript, Tailwind CSS, and ShadCN UI.

---

## Step 1: Choose an Aesthetic Direction

Commit fully to ONE direction before writing any code:

| Direction | Feel | Use For |
|-----------|------|---------|
| **Minimalist** | Clean, generous whitespace, monochromatic | Premium SaaS, professional services |
| **Bold/Maximalist** | Rich layers, vivid colors, dynamic animations | Creative agencies, youth brands |
| **Retro-Futuristic** | Geometric, neon, glitch, monospace fonts | Gaming, dev tools, tech startups |
| **Organic** | Soft shapes, earth tones, natural motion | Wellness, sustainability, food |
| **Editorial** | Strong type hierarchy, asymmetric grids | Media, content platforms |
| **Brutalist** | Intentionally raw, system fonts, high contrast | Art, fashion, counter-culture |

**Key**: Intentionality > intensity. Execute your chosen direction consistently across all 11 elements.

---

## Step 2: Define the Design System

Before coding, decide:

**Typography** — choose distinctive fonts (NOT Inter/Roboto/Arial/system-ui):
- Display: Space Grotesk, Clash Display, Syne, DM Serif Display, Fraunces, Unbounded
- Body: DM Sans, General Sans, Geist, Manrope, Switzer
- Scale: H1 4–6rem → H2 3rem → H3 2rem → Body 1rem

**Color** — define as CSS variables:
- Dominant (60%): Primary brand color
- Accent (10%): High-contrast CTA color
- Neutral (30%): Grays/earth tones
- Avoid: Purple gradients on white (overused AI aesthetic)

**Motion**:
- Page load: Staggered fade-in (title → subtitle → CTA, each 100–200ms delayed)
- Scroll: Fade-up on enter via Intersection Observer
- Hover: Scale, shadow, or color shift — surprise and delight
- Performance: Use `transform` and `opacity` (GPU-accelerated) — never `width`/`height`

---

## The 11 Essential Elements

Every landing page must include all 11. Each has a functional requirement (conversion) and a design requirement (memorability).

| # | Element | Functional Requirement | Design Excellence |
|---|---------|----------------------|-------------------|
| 1 | URL | SEO-optimized, descriptive slug | — |
| 2 | Header | Logo top-left, navigation | Sticky with blur-on-scroll; animated logo load |
| 3 | Hero Title + Subtitle | Clear value prop, keywords in H1 | Massive (4–6rem), distinctive display font, gradient or outlined text |
| 4 | Primary CTA | Button in hero | Pill shape, micro-interaction on hover, entrance animation after title |
| 5 | Social Proof | Reviews, ratings, user count | Huge animated numbers, overlapping avatars, custom star styling |
| 6 | Images/Videos | Product/service demonstration | Device mockups, 3D tilt, parallax scroll; never stock photos |
| 7 | Benefits/Features | 3–6 key advantages with icons | Asymmetric layout, custom icon treatment, staggered scroll animation |
| 8 | Testimonials | 4–6 authentic reviews with photos | Masonry or carousel, gradient card borders, oversized quote marks |
| 9 | FAQ | 5–10 questions with accordion | Smooth expand/collapse, rotating chevron, two-column on desktop |
| 10 | Final CTA | Bottom-of-page conversion | Full-width dramatic section, even bigger button, urgency elements |
| 11 | Footer | Contact info, legal links | Multi-column, social hover effects, newsletter signup |

**Avoid generic patterns**: boring 3-column feature grids, default yellow stars, white background with no visual interest, perfectly centered symmetric layouts on every section, stock photos of people pointing at laptops.

---

## Technology Stack

```bash
# Required
Next.js 14+ (App Router) | TypeScript | Tailwind CSS | ShadCN UI

# Install ShadCN components
npx shadcn-ui@latest add button card accordion badge avatar separator input
```

**ShadCN is a starting point** — customize heavily. Modify component files, add Tailwind variants, create brand-specific wrappers.

---

## Project Structure

```
landing-page/
├── app/
│   ├── layout.tsx        # metadata, fonts
│   ├── page.tsx          # composes all sections
│   └── globals.css       # CSS variables + design system
├── components/
│   ├── Header.tsx        # Element 2
│   ├── Hero.tsx          # Elements 3, 4, 5
│   ├── MediaSection.tsx  # Element 6
│   ├── Benefits.tsx      # Element 7
│   ├── Testimonials.tsx  # Element 8
│   ├── FAQ.tsx           # Element 9
│   ├── FinalCTA.tsx      # Element 10
│   └── Footer.tsx        # Element 11
└── public/images/
```

---

## Implementation Workflow

**1. Design system first** (before any code):
```css
:root {
  --font-display: 'Your Display Font';
  --font-body: 'Your Body Font';
  --color-primary: #xxx;
  --color-accent: #xxx;
  --duration-medium: 300ms;
  --easing: cubic-bezier(0.4, 0, 0.2, 1);
}
```

**2. SEO metadata** in `layout.tsx`:
```typescript
export const metadata: Metadata = {
  title: 'Keyword-Rich Title | Brand',
  description: 'Compelling description with keywords',
  openGraph: { title, description, images: ['/og.jpg'] },
};
```

**3. Build components in order**: Header → Hero (with animations) → Media → Benefits → Testimonials → FAQ → FinalCTA → Footer.

**4. Animation pattern** (Intersection Observer):
```typescript
useEffect(() => {
  const observer = new IntersectionObserver(
    ([entry]) => { if (entry.isIntersecting) setVisible(true); },
    { threshold: 0.1 }
  );
  if (ref.current) observer.observe(ref.current);
  return () => observer.disconnect();
}, []);
```

**5. Performance checklist**: Images use `next/image` with `priority` on hero. Fonts use `next/font`. No layout shifts (set explicit width/height). Core Web Vitals: LCP <2.5s, CLS <0.1, FID <100ms.
