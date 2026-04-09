---
name: final-website-refiner
description: |
  Transforms raw first-draft website code into an ultra-premium, animated,
  fully-customized website deployed to Cloudflare Pages. Use when the user
  says "refine this website", "polish this site", "final website refiner",
  "make this website premium", "customize this website", or provides raw
  React/JSX code and asks for a production-ready version. Reads business
  intelligence, design prompts, and brand extraction from SharpSites/Templates
  to produce a fully personalized, deployed website.
---

# Final Website Refiner

Transforms raw first-draft website code into an ultra-premium, animated, fully-customized website deployed to Cloudflare Pages at `{business-slug}.pages.dev`.

---

## Triggers

- User provides raw website code and asks to refine/polish/finalize
- "final website refiner", "refine this website", "make this premium"
- User provides a first draft and wants a production-ready deployed version

---

## Phase 1 — Intelligence Extraction

### 1.1 Parse the raw code
The raw `App.jsx` already contains business data. Extract:
- **Business name** — from `<h3>`, `<h1>`, navbar text, footer brand
- **Google Maps embed URL** — from `<iframe src="...">`
- **Addresses** — from contact sections, footer `<li>` items
- **Phone numbers** — from tel: links or text
- **Email** — from mailto: or text

### 1.2 Reverse-search Templates folder
```bash
ls /Users/theritiksharma1/Library/CloudStorage/GoogleDrive-ritiksharma3479@gmail.com/My\ Drive/Fight\ to\ Freedom/SharpSites/Templates/
```
Fuzzy-match the extracted business name to a subfolder.

### 1.3 Read ALL files in the matched folder
Every file is critical context. Read each one in its entirety:

**`business_intelligence.md`** — Sections to extract:
1. Business Overview → full name, aliases, established year, branches, principal, curriculum, motto, age range, student-teacher ratio, operating hours
2. Contact & Location → all branch addresses with full formatting, all phone numbers, email, Google Maps link
3. Services & Programs → core programs with age ranges, IPC curriculum structure (6 learning areas), special programs (Young Chefs Academy, Engineering for Kids, Jolly Phonics, etc.), fee structure (monthly + annual)
4. Customer Reviews → platform ratings (JustDial, Edustoke, Ribblu), individual parent quotes with names, key sentiment themes
5. Brand Tone → core values, brand voice descriptors, philosophy text
6. Visual Identity → existing color palette if any, photography style, available image URLs from JustDial/Edustoke/MouthShut
7. Facilities → amenities table (AC classrooms, CCTV, playground, swimming, etc.)
8. Competitor Analysis → competitor names and differentiators
9. Press Mentions → DNA India, LBB listings
10. Directory Presence → which directories list the business
11. Key Takeaways → USPs for messaging, recommended website sections, Google Maps embed details

**`website_design_prompt.md`** — Sections to extract:
1. Visual Design Direction:
   - Color palette table (role → hex → reasoning)
   - Typography table (level → font → weight → desktop size → mobile size)
   - Shape language (border-radius system)
   - Micro-interactions spec (button hover, card hover, link hover, scroll animation easing)
2. Page Structure — exact layout for every page (Home, About, Programs, Gallery, Admissions, Contact)
3. Component Specs — interactive card patterns (Diagnostic Shuffler, Telemetry Typewriter, Cursor Protocol)
4. Animation Specs — trigger, easing, duration for each animation type
5. SEO Requirements — title tag, meta description, schema markup types
6. Conversion Optimization — CTA text, trust signals, social proof elements
7. Content Tone — do/don't guidelines

**`reference_brand_extraction.json`** — Fields:
- `branding.colors` → primary, accent, background, textPrimary
- `branding.typography` → fontFamilies, fontSizes (h1, h2, body)
- `branding.spacing` → baseUnit, borderRadius
- `branding.personality` → tone, energy, targetAudience
- `secondary_reference` if present

### 1.4 GSD Planner
Read `~/.gemini/antigravity/skills/gsd-planner/SKILL.md` and break remaining phases into executable, verifiable tasks.

---

## Phase 2 — Image Sourcing

### 2.1 Catalog every available real image
Extract ALL image URLs from `business_intelligence.md` Section 6 (Visual Identity) and Section 11 (Directory Presence):
- JustDial listing photos (format: `content.jdmagicbox.com/...`)
- Edustoke cover photos (format: `storage.googleapis.com/cdn-edustoke/...`)
- MouthShut images (format: `image3.mouthshut.com/...`)
- Google Maps profile photos — search using Firecrawl MCP or web search: "[Business Name] [Location]" → extract photo URLs

### 2.2 Apply the image decision matrix

| Real Images Found | Action |
|---|---|
| **≥ 6 real images** | Use EXCLUSIVELY real images. Zero AI generation. This is the best outcome — real photos create the strongest personalization for the decision maker. |
| **1–5 real images** | Use ALL real images + generate exactly **2–3 AI images** to fill gaps. AI images must be customized to match the real school's visual style. |
| **0 real images** | Generate ALL images via AI. Every single image must be customized to the specific business — never generic. |

### 2.3 AI image customization protocol
When generating AI images, follow this exact process:

**Step A — Study available visual clues:**
- If ANY real photos exist, study them for: wall colors, furniture type (wooden/plastic), play equipment style, flooring type, classroom lighting, decorative elements
- If a logo exists, note its colors and style
- If nothing visual exists, use the color palette from `website_design_prompt.md`

**Step B — Craft business-specific prompts:**
- ALWAYS reference the specific business: "Indian preschool matching the interior style of [Business Name] in [Location]"
- Must be culturally accurate (e.g., Indian pre-school relevant age and data images).
- Include visual details from Step A: "with [actual wall color] walls, [furniture type], [equipment type]"
- Add demographic accuracy: "diverse Indian children aged 2-4, warm natural lighting, modern professional educational environment"
- Add quality keywords: "professional photography, shallow depth of field, warm color temperature, 4K quality"

**Step C — Never do these:**
- Never use generic prompts like "happy children playing"
- Never use non-Indian children for Indian preschools
- Never use neon/unrealistic lighting
- Never use the same prompt for multiple images — vary the scene

### 2.4 Image placement map
Every website needs images in these locations (minimum):
| Location | Type | Count |
|---|---|---|
| Hero background | Full-bleed with gradient overlay | 1 |
| About page | Philosophy/interior shot with ParallaxImage | 1 |
| Innovation Programs | One per program (2 minimum) | 2 |
| Gallery page | Masonry grid | 6+ |
| Total minimum | | 10+ |

---

## Phase 3 — UI/UX Chroma X Design System (MANDATORY)

### 3.1 Apply UI/UX Chroma X guidelines
```bash
# Execute UI/UX Chroma X principles
# Chroma X enforces:
# 1. 3D liquid glass effects (like iOS 26) throughout the website components.
# 2. Professional, premium, and refined color palettes suitable for the specific industry.
# 3. High-quality, culturally relevant imagery.
python3 ~/.gemini/antigravity/skills/ui-ux-pro-max/scripts/search.py \
  "{business_type} {industry} {style_keywords} premium chroma-x 3d-glass" \
  --design-system -p "{Business Name}"
```
Extract product type, industry, and keywords from `website_design_prompt.md` Section 2 (Target Audience) and Section 3 (Visual Design Direction).

### 3.2 Priority hierarchy
When design system recommendations conflict:
1. **`website_design_prompt.md`** wins — it was tailored for this exact business
2. **UI/UX Chroma X** supplements — fills gaps the prompt didn't cover and adds 3D/glass effects.
3. **`reference_brand_extraction.json`** inspires — use for sizing/spacing hints

### 3.3 Supplementary UX searches
```bash
python3 ~/.gemini/antigravity/skills/ui-ux-pro-max/scripts/search.py "animation accessibility" --domain ux
python3 ~/.gemini/antigravity/skills/ui-ux-pro-max/scripts/search.py "hero social-proof testimonial" --domain landing
python3 ~/.gemini/antigravity/skills/ui-ux-pro-max/scripts/search.py "preschool education warm" --domain style
```

---

## Phase 4 — Website Customization (The Core)

Read `~/.gemini/antigravity/skills/gsd-executor/SKILL.md` to execute methodically.

### 4.1 GlobalStyles injection
Every website starts with a `<GlobalStyles />` component that injects:
```jsx
const GlobalStyles = () => (
    <style>{`
    @import url('https://fonts.googleapis.com/css2?family=...');

    :root {
      --primary: #HEX;       /* from website_design_prompt.md palette */
      --accent: #HEX;
      --background: #HEX;
      --surface: #HEX;
      --text-primary: #HEX;
      --text-muted: #HEX;
      --success: #HEX;
    }

    body {
      color: var(--text-primary);
      font-family: 'BodyFont', sans-serif;
      overflow-x: hidden;
      -webkit-font-smoothing: antialiased;
      background-color: var(--background);
    }

    .font-display { font-family: 'DisplayFont', serif; }
    .font-heading { font-family: 'HeadingFont', sans-serif; }
    .font-mono { font-family: 'MonoFont', monospace; }

    /* Micro-interactions (GPU-only) */
    .btn-hover-effect {
      transition: transform 0.3s cubic-bezier(0.25, 0.46, 0.45, 0.94);
      will-change: transform;
    }
    .btn-hover-effect:hover { transform: scale(1.03); }

    .card-hover-effect {
      transition: transform 300ms cubic-bezier(0.25, 0.46, 0.45, 0.94),
                  box-shadow 300ms ease;
      will-change: transform, box-shadow;
    }
    .card-hover-effect:hover {
      transform: translateY(-4px);
      box-shadow: 0 10px 25px -5px rgba(0,0,0,0.05);
    }

    /* Lenis Smooth Scroll */
    html.lenis, html.lenis body { height: auto; }
    .lenis.lenis-smooth { scroll-behavior: auto !important; }
    .lenis.lenis-stopped { overflow: hidden; }
    .lenis.lenis-scrolling iframe { pointer-events: none; }
  `}</style>
);
```

### 4.2 Animation components (copy verbatim)
These four components are the COMPLETE animation engine. No other animation patterns needed.

**FadeUp** — wrap every `<section>`:
```jsx
const FadeUp = ({ children, delay = 0, className = "" }) => {
    const el = useRef(null);
    useLayoutEffect(() => {
        let ctx = gsap.context(() => {
            gsap.fromTo(el.current,
                { y: 30, opacity: 0 },
                { y: 0, opacity: 1, duration: 0.8, delay,
                  ease: "power3.out",
                  scrollTrigger: { trigger: el.current, start: "top 85%",
                    toggleActions: "play none none none" }
                });
        }, el);
        return () => ctx.revert();
    }, [delay]);
    return <div ref={el} className={`will-change-transform ${className}`}>
      {children}
    </div>;
};
```

**StaggerGroup** — wrap card grids, lists:
```jsx
const StaggerGroup = ({ children, className = "" }) => {
    const el = useRef(null);
    useLayoutEffect(() => {
        let ctx = gsap.context(() => {
            gsap.fromTo(el.current.children,
                { y: 30, opacity: 0 },
                { y: 0, opacity: 1, duration: 0.8, stagger: 0.1,
                  ease: "power3.out",
                  scrollTrigger: { trigger: el.current, start: "top 85%",
                    toggleActions: "play none none none" }
                });
        }, el);
        return () => ctx.revert();
    }, []);
    return <div ref={el} className={className}>{children}</div>;
};
```

**ParallaxImage** — hero/feature images:
```jsx
const ParallaxImage = ({ src, alt, className }) => {
    const el = useRef(null);
    const imgRef = useRef(null);
    useLayoutEffect(() => {
        let ctx = gsap.context(() => {
            gsap.fromTo(imgRef.current,
                { yPercent: -15 },
                { yPercent: 15, ease: "none",
                  scrollTrigger: { trigger: el.current,
                    start: "top bottom", end: "bottom top", scrub: true }
                });
        }, el);
        return () => ctx.revert();
    }, []);
    return (
        <div ref={el} className={`overflow-hidden relative ${className}`}>
            <img ref={imgRef} src={src} alt={alt}
                className="absolute inset-0 w-full h-[130%] object-cover
                           -top-[15%] will-change-transform"
                loading="lazy" />
        </div>
    );
};
```

**PageTransition** — wrap each page component's return:
```jsx
const PageTransition = ({ children }) => {
    const el = useRef(null);
    useLayoutEffect(() => {
        let ctx = gsap.context(() => {
            gsap.fromTo(el.current,
                { opacity: 0, y: 15 },
                { opacity: 1, y: 0, duration: 0.6, ease: "power2.out" });
        }, el);
        return () => ctx.revert();
    }, []);
    return <div ref={el} className="will-change-transform">{children}</div>;
};
```

### 4.3 Lenis initialization (App-level)
```jsx
const lenisRef = useRef(null);

useEffect(() => {
    const lenis = new Lenis({
        duration: 1.2,
        easing: (t) => Math.min(1, 1.001 - Math.pow(2, -10 * t)),
        smooth: true, smoothTouch: false,
        touchMultiplier: 2,
    });
    lenisRef.current = lenis;
    lenis.on('scroll', ScrollTrigger.update);
    gsap.ticker.add((time) => lenis.raf(time * 1000));
    gsap.ticker.lagSmoothing(0);
    return () => lenis.destroy();
}, []);
```

### 4.4 Scroll-to-top (CRITICAL for SPA with Lenis)
```jsx
// Requires lenis to be stored in a ref: const lenisRef = useRef(null);
useEffect(() => { 
  if (lenisRef.current) {
    lenisRef.current.scrollTo(0, { immediate: true });
  } else {
    window.scrollTo(0, 0); 
  }
}, [activeTab]);
```

### 4.5 Replace ALL business data
Map every piece from `business_intelligence.md` to the code:

| Data Point | Source Section | Where in Code |
|---|---|---|
| Business name, aliases | §1 Business Overview | Navbar brand, Footer brand, `<title>`, all headings |
| Motto/tagline | §1 | Hero subtitle, Footer tagline |
| Established year | §1 | Trust Bar badge, Footer, About timeline |
| Total branches | §1 | Footer "X Branches Active", Contact intro |
| Principal name + title | §1 | About page Leadership section |
| Curriculum name + details | §3 | Hero subtitle, About IPC section, Programs intro |
| Student-teacher ratio | §1 | Trust Bar badge, Feature Card 3 |
| Operating hours | §1 | Contact page |
| All branch addresses | §2 | Footer, Contact page (each branch separately) |
| All phone numbers | §2 | Footer, Contact page, CTA buttons |
| Email | §2 | Footer, Contact page |
| Google Maps link | §2/§12 | Footer `<iframe>`, Contact page `<iframe>` |
| Core programs + ages | §3 | Programs Overview cards (Home), Programs page cards |
| Special programs | §3 | Innovation Programs section (with images) |
| Fee structure | §3 | Admissions page fee table |
| Parent reviews (with names) | §4 | Testimonial section |
| Platform ratings | §4 | Trust Bar badge "X/5 Rating" |
| Brand philosophy text | §5 | About page Philosophy section (full quote) |
| Facilities list | §8 | About page or dedicated Facilities section |
| USPs | §12 | Trust Bar, Feature Cards, CTA sections |
| Competitors (info only) | §9 | Internal context — don't display |

### 4.6 Replace ALL images
Per Phase 2 decision. For each `<img>`:
- Set `src` to the real or AI-generated image URL
- Set `alt` to a descriptive text referencing the business
- Add `loading="lazy"` for below-fold images
- Use `object-cover` for consistent sizing
- Wrap hero/feature images in `<ParallaxImage>` component

### 4.7 Navbar — "The Floating Island"
Exact pattern (proven working):
- `fixed top-4 left-1/2 -translate-x-1/2 w-[95%] max-w-6xl z-50`
- Pill-shaped: `rounded-full px-6 py-4`
- **Morph on scroll:** transparent at hero top → `bg-[background]/80 shadow-lg border` when scrolled
- Scroll detection via `useEffect` + `window.scrollY > 50`
- Contains: Logo (text-based brand initials in circle + brand name), nav links array, CTA button (accent color pill)
- **Mobile:** hamburger toggle → full-screen overlay (`fixed inset-0 bg-[primary] z-40`)
- Mobile menu items call `setActiveTab(link)` + `setMobileMenuOpen(false)` + `window.scrollTo(0,0)`

### 4.8 Hero section
- `h-[100dvh]` full viewport
- Background: `<ParallaxImage>` with real venue photo + `opacity-60`
- Gradient overlay: `bg-gradient-to-t from-[primary] via-[primary]/80 to-transparent mix-blend-multiply`
- Content positioned: `max-w-7xl mx-auto px-6 pt-32`, inner `max-w-3xl`
- Typography contrast: Line 1 in `font-heading font-bold text-4xl md:text-5xl lg:text-6xl`, Line 2 in `font-display font-bold italic text-6xl md:text-7xl lg:text-[100px] text-[accent]`
- GSAP stagger using `textRef.current[]` array (y:40→0, opacity:0→1, stagger:0.08)
- CTA: accent-colored pill button with shadow

### 4.9 Trust Bar
- `bg-[primary]` horizontal strip below hero
- 4 badges with Lucide icons (Award, CheckCircle2, Star, Users) in `font-mono text-sm`
- Content from USPs in `business_intelligence.md` §12

### 4.10 Interactive feature cards
Three cards derived from the business's USPs:

**Card 1 — Diagnostic Shuffler:** Auto-cycling vertical text carousel (2.5s interval). Items from the business's curriculum/programs. `translateY` + `opacity` + minimal `blur(2px)`. Spring transition.

**Card 2 — Telemetry Typewriter:** Character-by-character typing effect with auto-delete cycle. Messages derived from the business's unique programs. Blinking accent cursor. "Live Feed" label with pulsing dot. Dark background card.

**Card 3 — Cursor Protocol:** Animated SVG cursor that moves across a weekly grid (M-S), clicks a day cell (scale press), highlights it. CSS `@keyframes moveCursor` animation. Day labels from the business's schedule.

### 4.11 Philosophy Manifesto
- Full-width, dark primary background
- Two contrasting statements: "Most [industry] focuses on: [common approach]." (smaller, muted) vs "We focus on: [differentiated approach]." (massive, display font, accent keyword)
- **Word-by-word GSAP reveal:** Split text into `<span className="phil-word">` per word, then `gsap.fromTo(words, {opacity:0.1, y:10}, {opacity:1, y:0, stagger:0.05, scrollTrigger: {scrub:1}})`

### 4.12 Programs section
- Tab or grid layout with cards for each program
- Each card: age badge (`font-mono text-xs` in colored pill), title (`font-heading bold`), description, feature checkmarks (CheckCircle2 icon), "Learn More" button
- One card can be inverted (primary bg, white text) for visual variety

### 4.13 Innovation Programs
- Two side-by-side image cards with overlay text
- Image: `object-cover` with `group-hover:scale-110 transition-transform duration-700`
- Gradient overlay: `bg-gradient-to-t from-black/80 to-transparent`
- Title and description positioned `absolute bottom-0 left-0 p-8`

### 4.14 Gallery page
- Masonry layout: `columns-1 md:columns-2 lg:columns-3 gap-6 space-y-6`
- Each image: `break-inside-avoid rounded-[24px] overflow-hidden group card-hover-effect`
- Hover: `group-hover:scale-105` on image + `group-hover:bg-black/10` overlay

### 4.15 Admissions page
- Two-column: Left = fee structure + requirements, Right = booking form
- Fee: rows in `bg-gray-50 rounded-2xl` with `flex justify-between`
- Requirements: checkmark list with `CheckCircle2` icons
- Form: dark primary bg, `rounded-[40px]`, white-on-dark inputs with `bg-white/10 border-white/20`, accent focus ring, branch selector dropdown

### 4.16 Contact page
- Two-column: Left = staggered contact cards, Right = Google Maps embed
- Each contact card: icon in colored rounded container + address/phone text
- Maps: `rounded-[40px] overflow-hidden shadow-xl border`, `<iframe>` with business search query

### 4.17 Footer
- `bg-[primary] text-[background] rounded-t-[48px] pt-20 pb-10`
- 4-column grid: Brand + tagline + "System Operational" status (pulsing green dot), Quick Links (onClick setActiveTab + scrollTo), Contact info (MapPin, Phone, Mail icons), Google Maps embed
- Bottom bar: copyright + established year in `font-mono text-xs opacity-60`

### 4.18 App component structure
```jsx
export default function App() {
    const [activeTab, setActiveTab] = useState('Home');
    // Lenis init (4.3)
    // Scroll-to-top (4.4)

    const renderPage = () => {
        // Ensure lenis is passed to components if they need scroll control
        switch (activeTab) {
            case 'Home': return <Home setActiveTab={setActiveTab} />;
            case 'About Us': return <AboutUs />;
            // ... all pages
        }
    };

    return (
        <div className="relative min-h-screen flex flex-col
                        selection:bg-[accent] selection:text-white overflow-hidden">
            <GlobalStyles />
            <Navbar activeTab={activeTab} setActiveTab={setActiveTab} />
            <main className="flex-grow flex flex-col pt-4">
                {renderPage()}
            </main>
            <Footer setActiveTab={setActiveTab} />
        </div>
    );
}
```

---

## Phase 4B — Performance Rules (ABSOLUTE)

The website MUST run smoothly on the cheapest Android phone with the weakest processor.

### Only animate these CSS properties:
- `transform` (translateY, scale, rotate)
- `opacity`

These are composited by the GPU — zero CPU paint cost.

### Never animate:
- `width`, `height`, `margin`, `padding`, `top`, `left`
- `box-shadow` (triggers paint)
- `filter: blur()` on large elements (CPU composite)

### Never use:
- `backdrop-blur` — CPU filter, kills Android performance
- `feTurbulence` / CSS noise overlays — CPU filter
- Three.js / React Three Fiber — entire 3D engine overhead
- Canvas particle effects — CPU-bound rendering
- Heavy SVG filters — CPU composite

### Always add:
- `will-change: transform` on animated elements
- `loading="lazy"` on below-fold images
- `overflow-x: hidden` on body and main container

---

## Phase 5 — Verification

Read `~/.gemini/antigravity/skills/gsd-verifier/SKILL.md`.

### 5.1 Build
```bash
npm run build  # Must exit code 0
```

### 5.2 Pre-delivery checklist
- [ ] No `backdrop-blur` anywhere in code
- [ ] No Three.js / R3F / canvas imports
- [ ] All animations use `transform` + `opacity` only
- [ ] Every `<img>` has descriptive `alt` text
- [ ] Every `<img>` has `loading="lazy"` (except hero)
- [ ] Every clickable element has `cursor-pointer`
- [ ] Hover transitions are 150–300ms
- [ ] Mobile responsive at 375px — no horizontal scroll
- [ ] Scroll-to-top fires on every page transition
- [ ] All image URLs resolve (no 404s)
- [ ] Google Maps iframe loads correctly
- [ ] Navbar morphs from transparent to solid on scroll
- [ ] Mobile hamburger menu opens and closes correctly
- [ ] Footer links trigger `setActiveTab` + `window.scrollTo(0,0)`
- [ ] All business data matches `business_intelligence.md` exactly
- [ ] No placeholder text remaining ("Lorem ipsum", "Your business", etc.)

---

## Phase 6 — Deploy

### 6.1 Build
```bash
npm run build
```

### 6.2 Deploy to Cloudflare Pages
```bash
npx --yes wrangler pages deploy dist --project-name {business-slug}
```

Derive `{business-slug}`:
- Lowercase the business name
- Replace spaces with hyphens
- Remove special characters (apostrophes, commas, dots)
- Example: "Learning Place International" → `learning-place-international`

### 6.3 Report
Provide: `{business-slug}.pages.dev`

---

## Progress Tracker

```markdown
- [ ] Phase 1 — Extract business name, find Templates folder, read ALL files
- [ ] Phase 2 — Source images (catalog real → apply decision matrix → generate AI if needed)
- [ ] Phase 3 — Run UI/UX Pro Max design system + supplementary searches
- [ ] Phase 4 — Customize website (GlobalStyles → animations → data → images → all sections)
- [ ] Phase 5 — Build verification + pre-delivery checklist (16 items)
- [ ] Phase 6 — Deploy to Cloudflare Pages, report live URL
```

## Error Recovery

| Error | Fix |
|---|---|
| Business folder not found in Templates | List all folders, ask user |
| Image URL returns 404 | Replace with AI-generated image |
| `npm run build` fails | Read error, fix imports/syntax, rebuild |
| Wrangler deploy fails | Run `wrangler login`, retry |
| Lenis not smooth | Check `gsap.ticker.lagSmoothing(0)` is set |
| Animations janky on mobile | Audit for non-GPU properties, remove `backdrop-blur` |
| ScrollTrigger not firing | Ensure Lenis `on('scroll', ScrollTrigger.update)` is connected |
