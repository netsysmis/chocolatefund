---
title: 'One-Page Hugo Informational Site with Contact'
type: 'feature'
created: '2026-07-27'
status: 'done'
route: 'one-shot'
---

# One-Page Hugo Informational Site with Contact

## Intent

**Problem:** The site had a standalone `index.html` bypassing Hugo, with no theme-driven content. Needed a proper Hugo-based one-page informational site for The Chocolate Future with hero, about, impact stats, call-to-action, services, and contact sections.

**Approach:** Created `data/en.yaml` to drive the Meghna theme sections, added missing theme partials (`bg-image.html`, `image.html`), removed root `index.html`, and configured `hugo.toml` menu and params.

## Suggested Review Order

1. `data/en.yaml` — All site content, section-by-section
2. `hugo.toml` — Menu links, logo removal, theme config
3. `layouts/partials/bg-image.html` — Background image partial (theme override)
4. `layouts/partials/image.html` — Image rendering partial (theme override)
5. `docs/index.html` — Generated output, verify all sections render
6. `assets/css/custom.css` — African earth tone theme overrides (unchanged, reference)

## Code Map

- `data/en.yaml` — Site content for all theme sections (banner, about, funfacts, cta, service, contact)
- `hugo.toml` — Site config, menu, params, plugins
- `layouts/partials/bg-image.html` — Theme override: background-image style attribute generator
- `layouts/partials/image.html` — Theme override: responsive image renderer with class support
- `assets/css/custom.css` — African earth tone color overrides (pre-existing, unchanged)
- `static/images/hero.jpg` — Hero and section background image (pre-existing)
- `docs/` — Hugo publish directory (generated output)

## Verification

**Commands:**
- `hugo --minify` -- expected: build succeeds, 7 pages, 0 errors

**Manual checks:**
- Hero section has background image and "Get in Touch" button linking to #contact
- About section shows 3 items: The Gap, The Opportunity, The Diaspora as the 17th Region
- Counter section shows 4 stats: 60, 3, 50, 2
- CTA section has "Contact Us" button linking to #contact
- Contact section shows email and location (no broken form)
- Nav menu links resolve to correct section IDs
