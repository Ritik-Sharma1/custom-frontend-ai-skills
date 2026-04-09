---
name: build-a-website
description: Master orchestration skill to build, design, test, and deploy a complete premium website from start to finish, incorporating SEO, GSAP animations, local assets, UI/UX intelligence, local SEO, full QA, and SEO auditing. Integrates local-seo, ui-ux-pro-max, website-qa, and seo-auditor as mandatory internal phases.
allowed-tools: Read, Write, Edit, Glob, Grep, Bash, generate_image
---

# Build a Website: Master Orchestration Protocol

This is the ultimate end-to-end skill for building, testing, and deploying a premium, multi-page website based on business intelligence and UI/UX prompts.

This skill encompasses frontend design thinking, SEO rules, image integration, UI/UX intelligence, local SEO, full QA, and strict testing requirements. The sub-skills `frontend-design`, `local-seo`, `ui-ux-pro-max`, `website-qa`, and `seo-auditor` are fully absorbed into this document — do NOT run them separately.

---

## Phase 1: Preparation & Asset Gathering

1. **Locate Business Intelligence**: Read `business_intelligence.md`, `website_design_prompt.md`, `ultimate_ui_prompt.md`, and `reference_brand_extraction.json` from the specific `SharpSites/templates/[Business Name]` folder.
2. **Local Image First Policy**: You MUST use local images found in `SharpSites/templates/[Business Name]/business images/` whenever possible.
   - If missing, use the native `generate_image` tool to create highly realistic images (e.g., "authentic Indian preschool classroom with natural lighting"). Do NOT use external API image generation MCPs, as the built-in capability is already optimal.
3. **Reference Awwwards Site**: Identify the exact Awwwards site used as a reference (ensure it's unique and hasn't been used for previous builds) and map its structural DOM layout to the current project.

---

## Phase 2: Technical Setup & Routing

1. **Scaffold React & Vite**: Initialize the project.
2. **Setup Tailwind & GSAP**: Install `tailwindcss`, `@gsap/react`, `gsap`, `react-router-dom`, `react-helmet-async`, `lucide-react`.
3. **MANDATORY `<ScrollToTop />` Rule**: Every single website you build MUST include a `ScrollToTop` component inside the React Router setup. Whenever a user clicks to navigate to a new page (e.g., from Home to About Us), the new page MUST load from the very top.

**File structure:**
```
/
├── index.html
├── src/
│   ├── App.jsx
│   ├── index.css
│   ├── pages/
│   │   ├── Home.jsx
│   │   ├── Services.jsx
│   │   ├── About.jsx
│   │   ├── Admissions.jsx
│   │   └── Contact.jsx
│   └── components/
│       ├── Navbar.jsx
│       ├── Footer.jsx
│       ├── WhatsAppButton.jsx
│       ├── Schema.jsx
│       ├── ScrollToTop.jsx
│       └── ContactFormPopup.jsx   ← MANDATORY on every site
├── public/
│   └── images/
└── package.json
```

---

## Phase 3: Frontend Design Thinking (from frontend-design)

> **One directive:** Do not build a website. Build a digital instrument. Every scroll intentional, every animation weighted. Eradicate all generic AI patterns.

### 3A. Constraint Analysis — ALWAYS FIRST

Before designing, answer these or ask the user:

| Constraint | Question | Why It Matters |
|------------|----------|----------------|
| **Timeline** | How much time? | Determines complexity |
| **Content** | Ready or placeholder? | Affects layout flexibility |
| **Brand** | Existing guidelines? | May dictate colors/fonts |
| **Tech** | What stack? | Affects capabilities |
| **Audience** | Who exactly? | Drives all visual decisions |

**Audience → Design Approach:**

| Audience | Think About |
|----------|-------------|
| **Gen Z** | Bold, fast, mobile-first, authentic |
| **Millennials** | Clean, minimal, value-driven |
| **Gen X** | Familiar, trustworthy, clear |
| **Boomers** | Readable, high contrast, simple |
| **B2B** | Professional, data-focused, trust |
| **Luxury** | Restrained elegance, whitespace |

### 3B. The Core Law of Premium UI

**One sentence:** A premium UI is one where every decision looks *intentional* and nothing looks *accidental*.

Expensive feels like:
- **Restraint** — Fewer colors, fewer fonts, fewer elements. What you *remove* signals taste.
- **Rhythm** — Spacing follows a mathematical scale. Nothing is "eyeballed."
- **Weight** — Typography has dramatic contrast between large and small. Light body, heavy headings.
- **Quiet confidence** — No exclamation marks, no rainbows, no "BEST IN CITY." Facts, not claims.
- **Material honesty** — Real photos, real data, real testimonials. Zero stock, zero clip art.

**The 400px test:** Screenshot any 400×400px crop. If it looks *designed*, the UI is premium. If any crop looks accidental, it's amateur.

### 3C. Anti-Patterns to Actively Avoid (MANDATORY)

| AI Default Tendency | Why It's Bad | Think Instead |
|---------------------|--------------|---------------|
| **Bento Grids (Modern Cliché)** | Used in every AI design | Why does this content NEED a grid? |
| **Hero Split (Left/Right)** | Predictable & Boring | How about Massive Typography or Vertical Narrative? |
| **Mesh/Aurora Gradients** | The "new" lazy background | What's a radical color pairing? |
| **Glassmorphism everywhere** | AI's idea of "premium" | How about solid, high-contrast flat? |
| **Deep Cyan / Fintech Blue** | Safe harbour | Why not Red, Black, or Neon Green? |
| **Dark background + neon glow** | Overused, AI look | What does the BRAND actually need? |
| **Rounded everything** | Generic/Safe | Where can edges be sharp or brutalist? |
| **Purple/violet everything** | ✅ PURPLE BAN | Ask for brand colors before defaulting |

### 3D. UX Psychology Laws (Internalize)

| Law | Principle | Application |
|-----|-----------|-------------|
| **Hick's Law** | More choices = slower decisions | ONE primary CTA per section |
| **Fitts' Law** | Bigger + closer = easier to click | 48px minimum CTAs |
| **Miller's Law** | ~7 items in working memory | Chunk content into groups |
| **Von Restorff** | Different = memorable | Make CTAs visually distinct |
| **Serial Position** | First/last remembered most | Hero = peak, Footer CTA = end |

**Emotional Design Levels:**
```
VISCERAL (instant)  → First impression: colors, imagery, overall feel
BEHAVIORAL (use)    → Using it: speed, feedback, efficiency
REFLECTIVE (memory) → After: "I like what this says about me"
```

### 3E. Layout — 8-Point Grid (Non-negotiable)

```
All spacing/sizing in multiples of 8:
├── Tight:  4px  (half-step for micro)
├── Small:  8px
├── Medium: 16px
├── Large:  24px–32px
├── XL:     48px–64px–80px
└── Section padding: 80–120px desktop, 48–64px mobile
```

Amateur tell: Padding values like `17px`, `23px`, `55px`. If it doesn't snap to 8px grid, reject it.

**Universal section order for service/local businesses:**
1. Navbar (sticky, floating pill)
2. Hero (full viewport, real photo, emotional headline, CTA)
3. Trust badges (Google rating, years, certifications — proof before promise)
4. Services/Programs (cards or tabs)
5. Differentiator/Philosophy (why you, not them)
6. Gallery (real photos, masonry)
7. Testimonials (specific outcomes, real names)
8. CTA section (form or booking)
9. FAQ (schema-ready)
10. Footer (map, contact, hours, social)

### 3F. Color Discipline — 60-30-10 + Max 3 Hues

```
60% → Primary/Background (calm, neutral base)
30% → Secondary (supporting areas)
10% → Accent (CTAs, highlights, attention)
```

| Color Psychology Need | Consider | Avoid |
|-----------------------|----------|-------|
| Trust, calm | Blue family | Aggressive reds |
| Growth, nature | Green family | Industrial grays |
| Energy, urgency | Orange, red | Passive blues |
| Luxury, creativity | Deep Teal, Gold, Emerald | Cheap-feeling brights |
| Clean, minimal | Neutrals | Overwhelming color |

**Pre-validated palettes:**

| Name | Primary | Accent | Background | Best For |
|------|---------|--------|------------|----------|
| Warm Garden | `#6B8F71` Sage | `#C4724E` Terracotta | `#FDFAF5` Cream | Preschools, nature |
| Trusted Blue | `#1E4D76` Navy | `#E8B44D` Gold | `#FAFAF7` Off-white | Institutional |
| Forest School | `#2D5016` Forest | `#C4B5E0` Lavender | `#FAF8F5` Linen | Waldorf/Outdoor |
| Modern Montessori | `#002855` Navy | `#A5E7E5` Teal | `#FFFFFF` White | Premium Montessori |
| Midnight Luxe | `#0D0D12` Obsidian | `#C9A84C` Champagne | `#FAF8F5` Ivory | Private club, luxury |
| Brutalist Signal | `#111111` Black | `#E63B2E` Signal Red | `#E8E4DD` Paper | Precision, control |
| Vapor Clinic | `#0A0A14` Deep Void | `#7B61FF` Plasma | `#F0EFF4` Ghost | Biotech, fintech |

### 3G. Typography — 3 Sizes That Feel Worlds Apart

| Level | Role | Size | Weight | Font Type |
|-------|------|------|--------|-----------|
| **Display** | Hero headline, section titles | 48–80px desktop, 32–48px mobile | 700–800 | Serif or rounded sans |
| **Body** | Paragraphs | 16–18px | 400 | Clean sans-serif |
| **Label** | Tags, badges, meta | 12–14px | 500–600, uppercase, tracked | Mono or body font |

**Font pairings:**

| Vibe | Heading | Body |
|------|---------|------|
| Premium luxury | Playfair Display 700 | Poppins 400 |
| Modern clean | Plus Jakarta Sans 700 | Inter 400 |
| Warm approachable | Fredoka 600 | Nunito 400 |
| Editorial authority | DM Serif Display 700 | Source Sans 3 |
| Dark luxurious | Inter 700 | Inter 400 (+ Playfair Italic accent) |
| Raw bold | Space Grotesk 700 | Space Grotesk 400 |

Anti-pattern: Never > 2 font families. Never decorative body fonts. Never Comic Sans.

### 3H. Interaction Feedback Defaults

| Element | Hover | Active/Click | Timing |
|---------|-------|-------------|--------|
| Buttons | `scale(1.03)`, bg shift | `scale(0.97)` | `200ms cubic-bezier(0.25,0.46,0.45,0.94)` |
| Cards | `translateY(-2px)`, shadow++ | N/A | `200ms ease` |
| Links | Color shift, `translateY(-1px)` | N/A | `150ms` |
| Nav items | Underline slide-in or color | N/A | `150ms` |
| Form inputs | Border color + subtle glow | N/A | `150ms` |

### 3I. Wow Factor — Review Before Writing Any Code

- [ ] Generous whitespace (luxury = breathing room)
- [ ] Subtle depth and dimension (not flat)
- [ ] Smooth, purposeful animations
- [ ] Attention to detail (alignment, consistency)
- [ ] Cohesive visual rhythm
- [ ] Custom elements, not all defaults
- [ ] Hero evokes intended emotion immediately
- [ ] Human elements (real faces, real stories)
- [ ] Social proof with specifics
- [ ] Professional real imagery (no stock, no clip art)

### 3J. Decision Loop (Every Design Task)

```
1. CONSTRAINTS  → Brand, timeline, tech, audience? If unclear → ASK
2. CONTENT      → What content exists? What is the hierarchy?
3. STYLE        → What's appropriate for context? If unclear → ASK (don't default!)
4. EXECUTION    → Apply principles above, check anti-patterns
5. REVIEW       → "Does this serve the user?"
                  "Is this different from my AI defaults?"
                  "Would I be proud of this?"
```

> **"Every 'safe' structure you choose brings you one step closer to a generic template. TAKE RISKS."**

---

## Phase 4: UI/UX Design Intelligence (from ui-ux-pro-max)

Before writing a single line of component code, run the design system generator:

```bash
python3 skills/ui-ux-pro-max/scripts/search.py "<business_type> <industry> <style_keywords>" --design-system -p "[Business Name]"
```

This outputs: pattern, style, colors, typography, effects, and anti-patterns. Use the result as the design system for the entire build.

### Design Rules (Non-Negotiable)

#### Visual Quality
- No emojis used as icons — use SVG (Lucide, Heroicons)
- All icons from consistent icon set, consistent `viewBox="0 0 24 24"` sizing
- Hover states must not cause layout shift — use `opacity` / `color` transitions
- Use `transition-colors duration-200` for all interactive state changes

#### Touch & Interaction
- All clickable elements: `cursor-pointer`
- Touch targets: minimum `44×44px`
- Disable submit buttons during async ops (`disabled={isSending}`)
- Clear error messages rendered near the problem field

#### Layout & Responsive (CRITICAL)
- `max-w-7xl` or `max-w-6xl` — consistent across all sections
- `viewport meta`: `width=device-width initial-scale=1`
- `min body text`: `16px` on mobile — use `text-base` / `rem` not `px`
- NO horizontal scroll on any breakpoint
- Responsive at: `375px`, `768px`, `1024px`, `1440px`
- Floating navbar: add `top-4 left-4 right-4` spacing, not `top-0 left-0`
- Account for fixed navbar height so content is never hidden beneath it

#### Typography & Color
- Line height: `1.5–1.75` for body text (`leading-relaxed`)
- Line length: limit to 65–75 characters per line (`max-w-prose`)
- Heading/body font personalities must match (e.g., serif display + clean sans body)
- Light mode text: minimum `#475569` (slate-600) for muted; `#0F172A` for body
- Glass cards in light mode: `bg-white/80` or higher — never `bg-white/10`
- Borders visible in light mode: `border-gray-200`, not `border-white/10`
- Color contrast: minimum `4.5:1` ratio for normal text (WCAG AA)

#### Animation
- GSAP `power3.out`, `ScrollTrigger` for entrance animations
- Micro-interactions: `150–300ms` duration
- Use `transform` / `opacity` — NEVER animate `width`, `height`, `top`, `left`
- Respect `prefers-reduced-motion` — wrap GSAP in a check or use `gsap.matchMedia()`

#### 3D Form Inputs — MANDATORY on ALL forms across the ENTIRE site

Every `<input>`, `<textarea>`, and `<select>` must use the 3D inset depth effect. Add this to `index.css`:

```css
/* 3D inset depth — light variant (use on cream/white backgrounds) */
.input-3d {
  background: var(--input-bg, #f5f5f0);
  border: 1px solid rgba(0,0,0,0.08);
  border-radius: 0.75rem;
  padding: 0.875rem 1.25rem;
  width: 100%;
  font-size: 0.875rem;
  box-shadow:
    inset 0 2px 6px rgba(0,0,0,0.10),
    inset 0 1px 2px rgba(0,0,0,0.06),
    0 1px 0 rgba(255,255,255,0.9);
  transition: box-shadow 0.2s ease, border-color 0.2s ease;
  outline: none;
}
.input-3d:focus {
  border-color: var(--brand-primary, #6B8F71);
  box-shadow:
    inset 0 2px 6px rgba(0,0,0,0.10),
    inset 0 1px 2px rgba(0,0,0,0.06),
    0 0 0 3px var(--brand-primary-10, rgba(107,143,113,0.12));
}

/* 3D inset depth — dark variant (use on dark/obsidian backgrounds) */
.input-3d-dark {
  background: rgba(255,255,255,0.07);
  border: 1px solid rgba(255,255,255,0.14);
  border-radius: 0.75rem;
  padding: 0.875rem 1.25rem;
  width: 100%;
  color: #fff;
  box-shadow:
    inset 0 2px 8px rgba(0,0,0,0.35),
    inset 0 1px 3px rgba(0,0,0,0.20),
    0 1px 0 rgba(255,255,255,0.05);
  transition: box-shadow 0.2s ease, border-color 0.2s ease;
  outline: none;
}
.input-3d-dark::placeholder { color: rgba(255,255,255,0.40); }
.input-3d-dark:focus {
  border-color: var(--brand-accent);
  box-shadow:
    inset 0 2px 8px rgba(0,0,0,0.35),
    inset 0 1px 3px rgba(0,0,0,0.20),
    0 0 0 3px var(--brand-accent-20);
}
```

Apply in JSX:
```jsx
<input className="input-3d" type="text" placeholder="Your Name *" />
<textarea className="input-3d" rows={4} />
<select className="input-3d">…</select>
```

---

## Phase 4: The Golden Five Pages (GEO & SEO Optimized)

Every build MUST contain these 5 pages to rank well on Generative Engine Optimization (GEO):

1. **Home Page (`/`)**: Main anchor, cinematic hero, full brand showcase.
2. **Services/Curriculum (`/services`)**: Hyper-detailed program breakdown.
3. **About Us / Faculty (`/about`)**: E-E-A-T signals, faculty profiles.
4. **Admissions (`/admissions`)**: Omit exact fees if regional norms require; maintain high-intent admission forms and process steps.
5. **Contact/Location (`/contact`)**: Exact embedded Google Map, NAP (Name, Address, Phone) consistency, operating hours.

---

## Phase 5: Cinematic Frontend Implementation

1. **Visual Texture**: Apply global noise texture (`<feTurbulence>`) in `index.css`.
2. **Micro-Interactions**: GSAP `power3.out` staggered reveal, magnetic buttons, `ScrollTrigger` interactions (sticky stacking cards, horizontal scrolling).
3. **Simulated UI Animations (MANDATORY APPLIED RULES)**:
   - **Bento Box Grids**: Design the features section using a Bento Box grid. Inside the cards, do not use static images. I want Simulated UI Micro-animations built with pure Tailwind CSS and SVGs. Build mini-interfaces (like fake cursors moving, typing effects, or sliding notification pop-ups) that automatically animate to explain the feature.
   - **Abstract SVGs**: Generate Abstract SVG Micro-animations for the icons/illustrations. Do not use static external images. Use Tailwind CSS to animate the SVG paths (like dashed spinning circles, pulsing nodes, or expanding rings) to visually symbolize the concepts.
4. **Component Architecture**:
   - Navbar (morphing glassmorphism — transparent on top, glass on scroll)
   - Footer (dark background with copyright + status indicator)
   - Feature Cards (Shuffler, Typewriter, Scheduler logic as needed)
   - `<WhatsAppButton />` fixed FAB at bottom-right (`wa.me/91XXXXXXXXXX`)
4. **Mobile-First Responsiveness (CRITICAL)**:
   - Functional Hamburger Menu using `Menu` / `X` from `lucide-react`
   - Touch-friendly targets: min `44×44px`
   - Readable `rem` font scaling
   - Single-column vertical stacking (`flex-col`) on small screens
   - Zero horizontal scroll

### ContactFormPopup — MANDATORY on every homepage

Every website MUST include a `ContactFormPopup` component:

- **Triggers 5 seconds after page load** on homepage only
- Uses `sessionStorage` — never re-shows after visitor closes
- **Submits silently via Web3Forms** (email to owner, user sees Thank You state — no WhatsApp visible)
- **Fully branded** to the site's colors, fonts, and tone
- Visible **✕ close button** + Escape key + backdrop click to dismiss
- Fields: Parent/Client Name *, Phone *, Specific-Context Field (e.g., Child's Age), Message (optional)
- CTA: `"Send Enquiry →"` using brand primary color button
- Footer line: `"Or call us directly: [phone]"` in muted text
- All inputs use `.input-3d` or `.input-3d-dark` class

**App.jsx wiring (single-file site):**
```jsx
import { useState, useEffect } from 'react';
import ContactFormPopup from './components/ContactFormPopup';

export default function App() {
  const [showPopup, setShowPopup] = useState(false);

  useEffect(() => {
    if (sessionStorage.getItem('popup_dismissed')) return;
    const t = setTimeout(() => setShowPopup(true), 5000);
    return () => clearTimeout(t);
  }, []);

  const closePopup = () => {
    setShowPopup(false);
    sessionStorage.setItem('popup_dismissed', '1');
  };

  return (
    <div>
      {/* all sections */}
      <ContactFormPopup show={showPopup} onClose={closePopup} />
    </div>
  );
}
```

**Multi-page (React Router):** Add an inner `HomepagePopup` component that reads `useLocation()` and only renders when `location.pathname === '/'`.

**Web3Forms key:** Replace `YOUR_WEB3FORMS_ACCESS_KEY` inside `ContactFormPopup.jsx` with the client's key from [web3forms.com](https://web3forms.com). Each client needs their own key (free: 250 submissions/month).

---

## Phase 6: JSON-LD Schema & Local SEO (from local-seo)

### Step 1 — Identify all NAP details
Extract: business name, full address (street, city, state, PIN), phone (+91 format), category, geo-coordinates, operating hours.

### Step 2 — NAP Consistency Checklist
- [ ] Business name exactly matches across all pages
- [ ] Phone in consistent format: `+91-XXXXX-XXXXX`
- [ ] Address in footer AND contact page (identical wording)
- [ ] Address links to Google Maps

### Step 3 — Inject LocalBusiness JSON-LD Schema

The `<Schema />` component must inject `application/ld+json` for:

```json
{
  "@context": "https://schema.org",
  "@type": "LocalBusiness",
  "name": "Business Name",
  "address": {
    "@type": "PostalAddress",
    "streetAddress": "123 Main St",
    "addressLocality": "City",
    "addressRegion": "State",
    "postalCode": "110001",
    "addressCountry": "IN"
  },
  "telephone": "+91-XXXXX-XXXXX",
  "url": "https://example.com",
  "geo": {
    "@type": "GeoCoordinates",
    "latitude": "28.6139",
    "longitude": "77.2090"
  },
  "openingHoursSpecification": [],
  "image": "https://example.com/og-image.jpg",
  "priceRange": "$$"
}
```

Also generate: `EducationalOrganization` (for schools), `hasOfferCatalog`, `Person` (Faculty), `BreadcrumbList`.

### Step 4 — On-Page Local Signals
- [ ] City/region name in H1 or H2
- [ ] City name in `<title>` tag: `"Best [Service] in [City] | [Brand]"`
- [ ] City name in meta description
- [ ] Location-specific content on service pages
- [ ] Embedded Google Maps iframe on `/contact` (exact school/business location)
- [ ] Local testimonials with city mentions
- [ ] FAQ schema with local questions

### Step 5 — India-Specific Additions
- WhatsApp floating FAB: `wa.me/91XXXXXXXXXX`
- "Call for Fee Details" (never show pricing in India for preschools/professional services)
- Transport / bus facility mention (if applicable)
- CCTV / safety messaging (preschools)
- `hreflang` if multilingual content planned

### Local Keyword Targets (auto-generate for each build)
| Pattern | Example |
|---------|---------|
| `[service] in [city]` | "preschool in Gurgaon" |
| `best [service] near [area]` | "best preschool near DLF Phase 3" |
| `[service] for [age] [city]` | "nursery for 2 year old Noida" |
| `[methodology] [service]` | "Montessori preschool Delhi" |
| `[service] with [feature]` | "preschool with CCTV Gurgaon" |

---

## Phase 7: SEO Audit (from seo-auditor)

Run this audit before deployment. For each item: 🔴 Critical / 🟡 Warning / 🟢 Pass.

### Title Tags
- [ ] Unique title per page (50–60 chars)
- [ ] Contains primary keyword + city
- [ ] Not duplicated across pages

### Meta Descriptions
- [ ] Present on all pages (150–160 chars)
- [ ] Contains primary keyword
- [ ] Compelling CTA language ("Schedule a visit today")

### Headings
- [ ] Single `<h1>` per page
- [ ] H1 contains primary keyword
- [ ] Proper H1 → H2 → H3 hierarchy (no skips)
- [ ] No empty heading tags

### Images
- [ ] All `<img>` have descriptive `alt` attributes (not "image1.jpg")
- [ ] WebP format used
- [ ] Explicit `width` and `height` on all images (prevents CLS)
- [ ] `loading="lazy"` on below-fold images

### Links
- [ ] Descriptive anchor text (not "click here")
- [ ] No broken internal links
- [ ] External links: `rel="noopener noreferrer"`

### Technical
- [ ] `<link rel="canonical">` on every page
- [ ] `<html lang="en">` set
- [ ] `robots.txt` accessible
- [ ] `sitemap.xml` linked in `robots.txt` and `<head>`
- [ ] Open Graph: `og:title`, `og:description`, `og:image`, `og:url`
- [ ] Twitter card tags
- [ ] No render-blocking CSS/JS without `async`/`defer`
- [ ] Google Fonts: `font-display: swap`

### Performance Signals
- [ ] First Contentful Paint < 1.8s
- [ ] Largest Contentful Paint < 2.5s
- [ ] Total page size < 3MB
- [ ] No render-blocking resources in `<head>`

**Auto-fix:** If issues found, apply fixes directly to source files — missing meta tags, heading fixes, alt text, canonical URLs, structured data.

---

## Phase 8: Internal Build Validation (NO EXCUSES)

1. **Pre-build Check**: Run `npm run build` locally. Zero missing imports, zero ESLint errors, zero React hooks violations before proceeding.
2. **Visual/DOM Check**: Use terminal + logic to confirm all components are correctly integrated in `App.jsx`.
3. **DO NOT DEPLOY BROKEN CODE**.

---

## Phase 9: Full QA Checklist (from website-qa)

### Visual & Layout
- [ ] Logo renders correctly on all pages
- [ ] Favicon set: 16×16, 32×32, apple-touch-icon
- [ ] No horizontal scrollbar on any viewport (375px, 768px, 1024px, 1440px)
- [ ] No orphaned text (single words on their own line)
- [ ] Images not stretched or pixelated
- [ ] Consistent spacing and alignment across pages
- [ ] No lorem ipsum or placeholder text visible

### Functionality
- [ ] All nav links work (no 404s)
- [ ] **ContactFormPopup appears after 5s on homepage** ← NEW mandatory check
- [ ] Popup close (✕ button, Escape key, backdrop click) all work
- [ ] After closing popup, page refresh does NOT re-show it (sessionStorage)
- [ ] **All form inputs show 3D inset depth effect** ← NEW mandatory check
- [ ] Form submission shows Thank You state (no page reload)
- [ ] All CTA buttons link to correct destinations
- [ ] Phone numbers are `tel:` links (clickable on mobile)
- [ ] Email addresses are `mailto:` links
- [ ] Address links to Google Maps
- [ ] WhatsApp FAB opens correct `wa.me` link in new tab
- [ ] Hamburger menu opens and closes on mobile
- [ ] ScrollToTop — navigating to new page loads from top

### Content
- [ ] No placeholder images
- [ ] Copyright year is current (2025)
- [ ] Privacy policy exists (if needed)
- [ ] Spelling and grammar checked
- [ ] NAP is consistent across all pages

### Performance
- [ ] Images: WebP, compressed, lazy-loaded
- [ ] No render-blocking resources
- [ ] LCP < 2.5s
- [ ] Total page < 3MB
- [ ] Google Fonts using `font-display: swap`

### SEO (cross-check with Phase 7 audit)
- [ ] Unique title per page
- [ ] Meta descriptions on all pages
- [ ] Single H1 per page
- [ ] `sitemap.xml` present
- [ ] `robots.txt` configured
- [ ] Open Graph tags present
- [ ] JSON-LD schema injected

### Security
- [ ] HTTPS
- [ ] No exposed API keys in source (check Web3Forms key is handled correctly)
- [ ] External links use `rel="noopener noreferrer"`

### Accessibility
- [ ] All images have alt text
- [ ] All form inputs have associated labels
- [ ] Focus rings visible on all interactive elements
- [ ] Color is not the only indicator of state
- [ ] `prefers-reduced-motion` respected in GSAP animations

### Popup QA (NEW — mandatory)
- [ ] Popup appears after exactly 5 seconds on homepage
- [ ] Popup is fully branded (colors, fonts match site)
- [ ] Popup inputs have 3D inset depth effect
- [ ] Popup submits → Thank You state shown, no reload
- [ ] Re-visit after close: popup does NOT reappear (sessionStorage)

---

## Phase 10: Deployment

1. **Always Update Wrangler**: Run `npm install -g wrangler@latest` before deploying.
2. **Cloudflare Pages**: Use Wrangler to deploy.
3. Project name: `[business-name]-demo`
4. Command:
   ```bash
   npm run build
   npx wrangler pages deploy dist --project-name="[business-name]-demo"
   ```
5. After deployment, open the live URL in Chrome DevTools and re-run the Phase 9 QA checklist on the production URL.

---

## Indian Legal & Financial Compliance (Conditional)

> **Only enforce the rules below when the business is a CA firm, Corporate Lawyer/Advocate, or Company Secretary (CS) firm operating in India. For all other business types, skip this section entirely.**

| Element | CA (ICAI) | Lawyer (BCI) | CS (ICSI) | All Others |
|---------|-----------|--------------|-----------|------------|
| Client Testimonials | ❌ Prohibited | ❌ Prohibited | ⚠️ Generic only | ✅ Allowed |
| Client Logos | ❌ Prohibited | ❌ Prohibited | ❌ Prohibited | ✅ Allowed |
| Fees / Pricing | ❌ Prohibited | ❌ Prohibited | ❌ In testimonials | ✅ Allowed |
| Superlatives ("Best", "Top") | ❌ Prohibited | ❌ Prohibited | ❌ Prohibited | ✅ Allowed |
| Case Studies | ❌ Prohibited | ❌ Prohibited | ⚠️ No fee/assignment details | ✅ Allowed |
| Aggressive CTAs | ❌ Pull-model only | ❌ Prohibited | ⚠️ Conservative | ✅ Allowed |
| Endorsements | ❌ Prohibited | ❌ Prohibited | ❌ Prohibited | ✅ Allowed |
| Comparison Claims | ❌ Prohibited | ❌ Prohibited | ❌ Prohibited | ✅ Allowed |

---

## Quick Reference: What's New vs Old

| Rule | Status |
|------|--------|
| Frontend Design Thinking phase (constraint analysis, UX laws, anti-patterns, wow-factor checklist) | 🆕 MANDATORY |
| ContactFormPopup on every homepage (5s delay, sessionStorage) | 🆕 MANDATORY |
| 3D inset depth on ALL form inputs (`.input-3d` / `.input-3d-dark`) | 🆕 MANDATORY |
| UI/UX Pro Max design system generation before coding | 🆕 MANDATORY |
| Full local SEO phase (NAP, schema, local keywords) | 🆕 MANDATORY |
| SEO audit before deployment | 🆕 MANDATORY |
| Full QA checklist including popup & 3D input checks | 🆕 MANDATORY |
| ScrollToTop component | ✅ Existing |
| Golden Five Pages | ✅ Existing |
| GSAP animations | ✅ Existing |
| WhatsApp FAB | ✅ Existing |
| Wrangler deploy to Cloudflare Pages | ✅ Existing |
