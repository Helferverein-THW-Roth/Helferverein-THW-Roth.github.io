# Agent Instructions – Helfervereinigung THW Roth Website

## Project Overview

Static website for the **Vereinigung der Helfer und Förderer des Technischen Hilfswerks (THW) Roth e.V.**, hosted on **GitHub Pages** from the `docs/` folder. No build tools, no bundler, no framework — pure hand-authored HTML and CSS.

## Structure

```
docs/              ← GitHub Pages root
├── index.html     ← Single-page site (sections: hero, über uns, fahrzeuge, mitgliedschaft, kontakt)
├── impressum.html ← Impressum + DSGVO Datenschutzerklärung
├── css/style.css  ← All styles, single file
└── media/         ← Images (JPG) and PDFs (membership form)
```

## Key Conventions

- **Language**: All content is in German (`lang="de"`)
- **Accessibility**: WCAG 2.1 Level AA required — semantic HTML5, ARIA labels, skip-link, `:focus-visible`, sufficient contrast
- **No external dependencies**: No CDN resources, no web fonts, no tracking, no cookies, no JavaScript frameworks
- **CSS custom properties** in `:root` for all colors — THW brand palette from [thw-roth.de](https://www.thw-roth.de):
  - `--thw-blue: #003399` (primary), `--thw-yellow: #FFEB00` (accent), `--thw-blue-dark: #1E2F66`
- **Section pattern**: `<section id="anchor" class="section" aria-labelledby="heading-id">` with `<div class="container">` wrapper
- **Responsive**: CSS Grid layouts collapse at 900px; mobile hamburger nav at 768px
- **Navigation**: Shared header/footer on both pages; mobile toggle via inline vanilla JS (IIFE)
- **Images**: Copyright belongs to the Helfervereinigung; `loading="lazy"` on all images

## DSGVO / Legal

The site must remain **static with zero tracking** (no cookies, no analytics, no external resources). This is a core DSGVO compliance requirement reflected in the Datenschutzerklärung. Any change that adds external requests (fonts, CDNs, iframes) would require updating `impressum.html`.
