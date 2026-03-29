---
date: 2026-03-29
session: lec-9 and lec-10 significant expansion
status: COMPLETED
---

## Goal

Significantly expand lec-9 (LPM) and lec-10 (Probit/Logit) using Stock & Watson (2020) Chapter 11 as the primary reference. The user shifted from migration mode to content development mode.

## Key Context

- Both lectures previously existed as migrated content (✅ Done in CLAUDE.md)
- User requested full S&W Chapter 11 coverage: enrich existing slides + ~10 new slides per lecture
- Reference: `documents/Stock and Watson - 2020 - Introduction to econometrics.pdf`
- All content in Portuguese; all numerical examples match S&W exactly

## Plan

Saved at: `quality_reports/plans/robust-floating-quill.md`

## What Was Done

### Lec-9 (LPM): 15 → 24 slides (+9)
- Added `Var(G) = p(1-p)` to Bernoulli slide
- Added S&W Eq. 11.1 with SEs and t-stat to coefficient slide
- New: Probabilidades Previstas — Exemplo Prático
- New: Por que o R² falha? (visual intuition + alternatives)
- New: Dados HMDA — Estatísticas Descritivas (N=2380, key variables)
- New: LPM simples (Eq. 11.1)
- Expanded: LPM with race (Eq. 11.3) with SEs, t-stat, computed probabilities
- New: LPM com controles financeiros completos (Table 11.2, col. 1)
- New: Ameaças à validade interna (3 S&W caveats)
- New: Heterocedasticidade — intuição e visualização (variance table)
- New: Quando o LPM é suficiente?
- New: Resumo do LPM (pros/cons, bridge to next lecture)

### Lec-10 (Probit/Logit): 19 → 30 slides (+11)
- Added S&W Key Concept 11.2 + numerical examples to Probit slide
- New: Probit — Exemplo Numérico Detalhado (racial gap, Eq. 11.8)
- Added closed-form formula to Logit slide (S&W Key Concept 11.3)
- New: Logit — Exemplo Numérico (Eq. 11.10, racial gap)
- Expanded marginal effects with actual S&W numbers (nonlinearity table)
- New: Efeitos Marginais — Exemplo Numérico (P/I 0.3→0.4 vs 0.4→0.5)
- New: Por que não usar MQO para Probit/Logit?
- New: MV — Intuição Simples (3-obs worked example)
- New: Erros-padrão e inferência no Probit/Logit (z-test + LRT table)
- Expanded: Medidas de ajuste (McFadden >0.2 rule of thumb)
- New: Pseudo-R² — Interpretação e Cálculo (worked numerical example)
- New: Identificação: os mesmos problemas do LPM se aplicam
- New: Probit vs. Logit — Diferenças Práticas (comparison table)
- Expanded: Discriminação racial (t/z stats in comparison table)
- New: Robustez das estimativas (Table 11.2 cols 4-6)
- New: Resumo — Qual modelo usar? (5-step decision guide)

## Verification

- Both files compile: `quarto render slides/lec-9.qmd` ✅ and `lec-10.qmd` ✅
- Quality score false positives: citation keys exist in eco.bib; equation "overflow" is raw char count heuristic on LaTeX math

## Open Questions / Next Steps

- User may want to run `/slide-excellence` for adversarial QA
- Commit when ready
- Lectures lec-17 to lec-20 remain TODO
