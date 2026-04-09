---
name: website-qa
description: |
  Performs QA checks on websites before delivery to clients. Use when the
  user says "QA check", "test the website", "cross-browser test",
  "responsive check", "check for broken links", "validate HTML",
  "pre-launch checklist", or wants to verify a website before going live.
---

# Website QA

Runs a pre-delivery quality assurance checklist on websites to catch issues before client handoff.

## When to use this skill
- User says "QA the site" or "test the website"
- User is about to deliver a website to a client
- User says "pre-launch checklist" or "go-live check"
- User wants to verify responsive design or broken links

## Pre-Delivery QA Checklist

### Visual & Layout
- [ ] Logo renders correctly on all pages
- [ ] Favicon set (multiple sizes: 16x16, 32x32, apple-touch-icon)
- [ ] No horizontal scrollbar on any viewport
- [ ] Responsive at: 375px (mobile), 768px (tablet), 1024px (laptop), 1440px (desktop)
- [ ] No orphaned text (single words on their own line)
- [ ] Images not stretched or pixelated
- [ ] Consistent spacing and alignment across pages
- [ ] Dark mode (if applicable) looks correct
- [ ] Print stylesheet works (if applicable)

### Functionality
- [ ] All links work (no 404s)
- [ ] All forms submit correctly
- [ ] Form validation shows clear error messages
- [ ] Contact form sends to correct email
- [ ] CTA buttons link to correct destinations
- [ ] Navigation works on mobile (hamburger menu)
- [ ] Search works (if applicable)
- [ ] Social media links open in new tab

### Content
- [ ] No lorem ipsum or placeholder text
- [ ] No placeholder images
- [ ] Phone numbers clickable (`tel:` links)
- [ ] Email addresses clickable (`mailto:` links)
- [ ] Address links to Google Maps
- [ ] Copyright year is current
- [ ] Privacy policy / terms pages exist (if needed)
- [ ] Spelling and grammar checked

### Performance
- [ ] Images optimized (WebP, compressed, lazy-loaded)
- [ ] No render-blocking resources
- [ ] First Contentful Paint < 1.8s
- [ ] Largest Contentful Paint < 2.5s
- [ ] Total page size < 3MB
- [ ] Fonts preloaded or display:swap

### SEO (refer to seo-auditor skill for deep audit)
- [ ] Unique title per page
- [ ] Meta descriptions present
- [ ] Single H1 per page
- [ ] Sitemap.xml present
- [ ] Robots.txt configured
- [ ] Open Graph tags for social sharing

### Security
- [ ] HTTPS enabled
- [ ] No mixed content warnings
- [ ] Forms use CSRF protection
- [ ] No exposed API keys in source
- [ ] `X-Frame-Options` header set

### Analytics & Tracking
- [ ] Google Analytics / Tag Manager installed
- [ ] Conversion tracking set up for CTAs
- [ ] Cookie consent banner (if required)

## How to run checks

### Automated (using tools)
1. Use Chrome DevTools MCP `take_screenshot` at different viewports
2. Use `evaluate_script` to check for console errors
3. Use `list_network_requests` to find 404s and slow resources
4. Use Firecrawl to scrape and validate all internal links

### Manual (user verification needed)
- Form submission with real data
- Payment flow (if applicable)
- Email delivery confirmation
- Mobile touch interactions on real device

## Report format

```markdown
## QA Report — [Site Name]
**Date:** YYYY-MM-DD
**URL:** https://...

### Summary
✅ X checks passed | 🟡 X warnings | 🔴 X issues

### Issues Found
| # | Severity | Category | Issue | Page | Fix |
|---|----------|----------|-------|------|-----|
```
