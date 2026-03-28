# CLAUDE.MD -- IBM0288 Microeconometria

**Project:** IBM0288 Microeconometria
**Institution:** IBMEC
**Instructor:** Prof. Raphael Gouvea
**Semester:** 2026.1
**Branch:** main

---

## Core Principles

- **Plan first** -- enter plan mode before non-trivial tasks; save plans to `quality_reports/plans/`
- **Verify after** -- render and confirm output at the end of every task
- **Single source of truth** -- Quarto `.qmd` is authoritative (no Beamer)
- **Quality gates** -- nothing ships below 80/100
- **[LEARN] tags** -- when corrected, save `[LEARN:category] wrong → right` to MEMORY.md

---

## Folder Structure

```
website_test/
├── CLAUDE.md                    # This file
├── _quarto.yml                  # Quarto website config (output: _site/, Netlify)
├── theme.scss                   # HTML website theme
├── index.qmd                    # Course homepage
├── schedule.qmd                 # Semester schedule
├── slides/                      # RevealJS lecture slides (lec-1.qmd ... lec-N.qmd)
│   ├── slides.scss              # Slide theme
│   └── images/lec-N/           # Images per lecture
├── section/                     # Section prep pages (section-1.qmd ...)
├── labs/                        # R practical labs (lab-0.qmd ...)
├── homeworks/                   # Problem sets and solutions
├── exams/                       # Exam files
├── help/                        # Support material
├── documents/                   # Templates, PDFs, bibliography, images
├── .claude/                     # Rules, skills, agents, hooks
├── scripts/                     # Utility scripts
├── quality_reports/             # Plans, session logs, merge reports
├── explorations/                # Research sandbox
└── master_supporting_docs/      # Reference papers and existing slides
```

---

## Commands

```bash
# Render full website (Netlify deploys _site/ automatically)
quarto render

# Render a single file
quarto render slides/lec-1.qmd

# Quality score
python scripts/quality_score.py slides/lec-N.qmd
```

---

## Quality Thresholds

| Score | Gate | Meaning |
|-------|------|---------|
| 80 | Commit | Good enough to save |
| 90 | PR | Ready for deployment |
| 95 | Excellence | Aspirational |

---

## Skills Quick Reference

| Command | What It Does |
|---------|-------------|
| `/proofread [file]` | Grammar/typo/overflow review |
| `/visual-audit [file]` | Slide layout audit |
| `/pedagogy-review [file]` | Narrative, notation, pacing review |
| `/review-r [file]` | R code quality review |
| `/slide-excellence [file]` | Combined multi-agent review |
| `/validate-bib` | Cross-reference citations |
| `/devils-advocate` | Challenge slide design |
| `/commit [msg]` | Stage, commit, PR, merge |
| `/lit-review [topic]` | Literature search + synthesis |
| `/research-ideation [topic]` | Research questions + strategies |
| `/review-paper [file]` | Manuscript review |
| `/data-analysis [dataset]` | End-to-end R analysis |
| `/learn [skill-name]` | Extract discovery into persistent skill |
| `/context-status` | Show session health + context usage |
| `/deep-audit` | Repository-wide consistency audit |

---

## Quarto CSS Classes (slides/slides.scss)

| Class       | Effect                                        | Use Case                        |
|-------------|-----------------------------------------------|---------------------------------|
| `.question` | Blue left-border, light blue bg               | Discussion/comprehension checks |
| `.poll`     | Gold left-border, light yellow bg             | In-class polls                  |
| `.appex`    | Blue left-border + padding, light blue bg     | Applied exercises               |
| `.small`    | 75% font size                                 | Dense content or footnotes      |

---

## Current Project State

| File | Topic | Status |
|------|-------|--------|
| `slides/lec-1.qmd` | Plano de Ensino | ✅ Done |
| `slides/lec-2.qmd` | Revisão de Probabilidade e Estatística | ✅ Done |
| `slides/lec-3.qmd` | Introdução à Inferência Causal | ✅ Done |
| `slides/lec-4.qmd` | Aleatorização e Experimentos | ✅ Done |
| `slides/lec-5.qmd` | Inferência Causal Baseada em Regressões | ✅ Done |
| `slides/lec-6.qmd` | Viés de Variável Omitida | ✅ Done |
| `slides/lec-7.qmd` | Dados em Painel: Efeitos Fixos | ✅ Done |
| `slides/lec-8.qmd` | Dados em Painel: Efeitos de Tempo | ✅ Done |
| `slides/lec-9.qmd` | Variável Dependente Limitada (1) | ✅ Done |
| `slides/lec-10.qmd` | Variável Dependente Limitada (2) | ✅ Done |
| `slides/lec-11.qmd` | Variáveis Instrumentais (1) | ✅ Done |
| `slides/lec-12.qmd` | Variáveis Instrumentais (2) | ✅ Done |
| `slides/lec-13.qmd` | Diferenças em Diferenças (1) | ✅ Done |
| `slides/lec-14.qmd` | Diferenças em Diferenças (2) | ✅ Done |
| `slides/lec-15.qmd` | Regressão Descontínua (1) | ✅ Done |
| `slides/lec-16.qmd` | Regressão Descontínua (2) | ✅ Done |
| `slides/lec-17.qmd` | Avanços Recentes em DiD (1) | 🔲 TODO |
| `slides/lec-18.qmd` | Avanços Recentes em DiD (2) | 🔲 TODO |
| `slides/lec-19.qmd` | Big Data e Machine Learning (1) | 🔲 TODO |
| `slides/lec-20.qmd` | Big Data e Machine Learning (2) | 🔲 TODO |
