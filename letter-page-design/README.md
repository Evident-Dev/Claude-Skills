# 📄 letter-page-design

A Claude skill for generating **print-ready, US Letter-sized HTML designs** — flyers, handouts, one-pagers, brochures, and multi-page documents that look great on screen and print perfectly on paper.

---

## What It Does

This skill tells Claude to produce HTML files locked to exactly **8.5 × 11 inches**, with proper print CSS, clean page breaks, and a fixed-canvas layout that never overflows or gets cut off. Each `.page` div maps to one printed sheet — stack multiple to build multi-page documents.

The skill enforces design quality standards: distinctive Google Font pairings (no Arial/Roboto defaults), CSS variable-driven color systems, compositional variety across pages, and editorial-style layouts over generic SaaS aesthetics.

### Output types it handles well
- Event flyers and promotional posters
- Business handouts and one-pagers
- Program brochures and multi-page packets
- Spec sheets and reference documents
- Agendas, rosters, price lists, and catalogs
- Cover pages, closing/CTA pages, and everything in between

---

## Why HTML Instead of Canva or Other Design Tools?

Claude designs **dramatically better in HTML and CSS** than in any drag-and-drop tool. It can execute precise layouts, custom typography, editorial grid systems, and print-safe CSS that would take significant manual effort in Canva — and the results are more distinctive, more controllable, and easier to iterate on. The output is a real file you own, not locked inside a platform.

---

## How to Use

Install the skill into your Claude environment, then make requests naturally:

```
"Make me a flyer for my photography studio open house"
"Create a 3-page event program for our annual gala"
"Design a letter-size handout summarizing our pricing"
"Make a printable checklist for onboarding new clients"
```

The skill triggers automatically on any request involving flyers, posters, handouts, one-pagers, printable documents, or 8.5×11 layouts.

---

## Exporting to PDF

Once Claude delivers the HTML file, export it to PDF in either of these ways:

**Browser:**
Open the file → `Cmd/Ctrl + P` → set Margins to **None** → Paper size to **Letter** → Save as PDF.

**Command line:**
```bash
chromium --headless --print-to-pdf=out.pdf --no-margins file://path/to/file.html
```

---

## File Structure

```
letter-page-design/
├── SKILL.md          # Skill definition and design rules read by Claude
└── assets/
    └── template.html # Base template Claude starts from
```

---

## Notes

- Best for **print and PDF** use cases. For interactive web UIs, dashboards, or scrolling pages, use the `frontend-design` skill instead.
- Claude reads `assets/template.html` as a starting point — it includes the page container, print CSS, paper grain texture, and typography scaffolding already wired up correctly.
