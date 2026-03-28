---
paths:
  - "slides/**/*.qmd"
  - "section/**/*.qmd"
  - "labs/**/*.qmd"
  - "homeworks/**/*.qmd"
---

# Single Source of Truth: Quarto-Native Project

**The `.qmd` file is the authoritative source for ALL content.** This project has no Beamer source.

## The SSOT Chain

```
Quarto .qmd (SOURCE OF TRUTH)
  ├── _site/ HTML output (derived — never edit directly)
  ├── slides/images/lec-N/ (static images referenced by slides)
  └── documents/references.bib (shared bibliography)

NEVER edit _site/ output directly.
ALWAYS edit the .qmd source, then re-render.
```

---

## Content Fidelity Checklist (for translated slides from IBM0288_old)

When translating a slide from the old format to the new IBM0288 format:

```
[ ] All slide content preserved (no slides dropped, no new slides invented)
[ ] All equations preserved with identical notation
[ ] All images copied to slides/images/lec-N/ and paths updated
[ ] Old CSS classes replaced: .highlight → .question/.appex, .rounded-box → .appex
[ ] YAML frontmatter matches lec-8.qmd conventions
[ ] Footer and logo paths correct
```

---

## Environment / CSS Parity

Before translating any old slide that uses custom CSS:

1. Check what classes are used in the old slide (`.highlight`, `.rounded-box`, `.button`)
2. Map to new classes in `slides/slides.scss`:
   - `.highlight` → `.question` or inline bold/color
   - `.rounded-box` → `.appex`
   - `.button` → standard Quarto link
3. If a new class is needed, add it to `slides/slides.scss` before writing the slide
