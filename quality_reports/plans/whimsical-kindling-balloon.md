# Plan: Configure Workflow + Migrate IBM0288 Course Website
**Status:** DRAFT
**Date:** 2026-03-28
**Session:** Initial setup + content migration for IBM0288 Microeconometria at IBMEC

---

## Context

This repo is a fork of the Claude Code academic workflow template. The goal is to:
1. Configure the workflow infrastructure for IBM0288 (IBMEC, Prof. Raphael Gouvea, 2026.1)
2. Copy `~/Documents/IBM0288` as-is into this repo (the reference "new format" — do NOT alter its content)
3. Identify missing slides from `schedule.qmd` and translate them from `~/Documents/microeconometria_IBM0288_old` into the new IBM0288 format
4. Deployment: **Netlify** (keep `output-dir: _site` — do not change to `docs/`)

---

## Missing Slides (from schedule.qmd)

Existing slides: **lec-1 through lec-8** (Intro, Stats, Causal Inference, Experiments, Regression, OVB, Panel FE, Panel Time FE)

Slides shown as `[ ]()` placeholders in schedule.qmd — need to be created:

| New file | Topic | Source in IBM0288_old |
|----------|-------|-----------------------|
| `slides/lec-9.qmd` | Modelos com variável dependente limitada (1) | `slides/binary/binary_1.qmd` |
| `slides/lec-10.qmd` | Modelos com variável dependente limitada (2) | `slides/binary/binary_2.qmd` |
| `slides/lec-11.qmd` | Variáveis instrumentais (1) | `slides/iv/IV_1.qmd` |
| `slides/lec-12.qmd` | Variáveis instrumentais (2) | `slides/iv/IV_2.qmd` |
| `slides/lec-13.qmd` | Diferenças em diferenças (1) | `slides/did/DiD_intuicao.qmd` |
| `slides/lec-14.qmd` | Diferenças em diferenças (2) | `slides/did/DiD.qmd` |
| `slides/lec-15.qmd` | Regressão descontínua (1) | `slides/rdd/RDD_Sharp.qmd` |
| `slides/lec-16.qmd` | Regressão descontínua (2) | `slides/rdd/RDD_Fuzzy.qmd` |
| `slides/lec-17.qmd` | Avanços recentes em dif-in-dif (1) | `slides/_panel/did.qmd` (draft) |
| `slides/lec-18.qmd` | Avanços recentes em dif-in-dif (2) | `slides/_panel/event-studies.qmd` (draft) |
| `slides/lec-19.qmd` | Big Data e Machine Learning (1) | `slides/_prediction/intro-sl.qmd` (draft) |
| `slides/lec-20.qmd` | Big Data e Machine Learning (2) | `slides/_prediction/regression-pt1.qmd` (draft) |

**Note:** lec-17 through lec-20 are marked red in schedule.qmd (advanced/optional topics). Source files are drafts — lower priority, migrate only if source quality is sufficient.

**Labs:** Missing labs (lab-5 through lab-8) are out of scope for this session.

---

## What the "new format" means for translated slides

When translating old slides (IBM0288_old) → new format (IBM0288), adopt:

**YAML frontmatter** (match existing lec-5 through lec-8 style):
```yaml
---
title: "Título da Aula"
subtitle: "IBM0288 - Microeconometria"
author: "Raphael Gouvea"
date: today
format:
  revealjs:
    theme: [default, slides.scss]
    logo: ../documents/images/ibmec_logo.png
    footer: "IBM0288 - Microeconometria | IBMEC"
    ... (match existing lecture headers)
---
```

**CSS classes:** replace old `.highlight`, `.rounded-box`, `.button` with new `.question`, `.poll`, `.appex`, `.small`

**Image paths:** update relative paths to `images/lec-X/` subdirectory

**Language:** keep Portuguese (pt-br)

**Content fidelity:** do NOT rewrite content — translate structure and styling only

---

## Execution Steps

### Step 1 — Create session log
`quality_reports/session_logs/2026-03-28_initial-setup.md`

### Step 2 — Configure workflow infrastructure
Files to update:
- `CLAUDE.md`: Fill in IBM0288, IBMEC, Prof. Raphael Gouvea, 2026.1; update Single Source of Truth → `.qmd`; update Folder Structure; update CSS classes table; remove Beamer compilation commands; update Current Project State
- `.claude/agents/domain-reviewer.md`: Customize 5 review lenses for microeconometrics/causal inference (econometric correctness, assumption sufficiency, code-theory alignment, citation fidelity, undergraduate accessibility)
- `.claude/rules/single-source-of-truth.md`: Update to say `.qmd` is authoritative (no Beamer)
- `.claude/rules/beamer-quarto-sync.md`: Add path scope `globs: ["Slides/*.tex"]` so it doesn't fire
- `.claude/rules/no-pause-beamer.md`: Add path scope `globs: ["Slides/*.tex"]` so it doesn't fire
- `.gitignore`: Add `_site/`, `_freeze/`, `renv/`, `.quarto/` if not already present

### Step 3 — Copy IBM0288 as-is into this repo
Using `cp -r` to copy faithfully:
- `_quarto.yml` (keep output-dir: _site — Netlify)
- `theme.scss`
- `index.qmd`, `schedule.qmd`, `project-description.qmd`, `project-tips-resources.qmd`
- `slides/` (all 8 lec-*.qmd + slides.scss + images/)
- `section/` (all 9 section-*.qmd)
- `labs/` (lab-0 through lab-4 + Data/ + images/)
- `homeworks/` (hw-1 through hw-4)
- `exams/AP1.qmd`
- `help/rubin.qmd`
- `documents/` (templates, PDFs, images, references.bib)

### Step 4 — Read existing lec-8.qmd as format reference
Before translating, read `slides/lec-8.qmd` from the new IBM0288 to understand exact YAML and structural conventions.

### Step 5 — Translate missing slides (lec-9 through lec-16)
For each slide:
1. Read source file from IBM0288_old
2. Read any referenced images
3. Write new `slides/lec-X.qmd` adopting new format (YAML, CSS classes, image paths)
4. Copy images to `slides/images/lec-X/`

Priority: lec-9, lec-10, lec-11, lec-12, lec-13, lec-14, lec-15, lec-16
Defer: lec-17 through lec-20 (advanced/red topics — assess source quality first)

### Step 6 — Update schedule.qmd links
Replace `[ ]()` placeholders with actual links:
- `[ ]()` for slides → `[💻️️](/slides/lec-X.html)`
- `[ ]()` for labs → `[⌨️](/labs/lab-X.html)`

### Step 7 — Verify compilation
Run `quarto render` from repo root.
Check that `_site/` is populated and all pages render.
Pay special attention to: image paths, MathJax equations, R code chunks in labs.

---

## Critical Files

| File | Action |
|------|--------|
| `CLAUDE.md` | Update all placeholders |
| `.claude/agents/domain-reviewer.md` | Customize for microeconometrics |
| `.claude/rules/single-source-of-truth.md` | Update to Quarto-native |
| `.claude/rules/beamer-quarto-sync.md` | Scope to Slides/*.tex |
| `.claude/rules/no-pause-beamer.md` | Scope to Slides/*.tex |
| `.gitignore` | Ensure _site/, _freeze/, renv/ excluded |
| `_quarto.yml` | Copy from IBM0288 (keep _site/) |
| `slides/lec-9.qmd` through `lec-16.qmd` | New — translated from IBM0288_old |
| `schedule.qmd` | Update `[ ]()` placeholders with real links |

---

## Verification Steps

1. `quarto render` completes without errors
2. `_site/index.html` renders correctly
3. `_site/slides/lec-9.html` through `lec-16.html` render as RevealJS
4. Schedule links resolve (no broken `[ ]()` entries for completed lectures)
5. Images load in translated slides
6. Math renders in translated slides
