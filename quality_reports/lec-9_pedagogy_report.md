# Pedagogical Review: lec-9.qmd
**Date:** 2026-03-29
**Reviewer:** pedagogy-reviewer (Agent 2)
**Topic:** Variável Dependente Binária — Modelo de Probabilidade Linear

## Narrative Arc Assessment

**Structure:** Motivation (binary Y examples) → Bernoulli distribution → LPM derivation → interpretation → HMDA empirical case → limitations → practical guidance → summary.

This is a textbook narrative arc: phenomenon → formalization → application → caveats. The arc is coherent and student-friendly.

**Pacing:** 26 slides for ~80 minutes = appropriate density.

---

## 13 Pedagogical Patterns Checklist

| Pattern | Status | Notes |
|---------|--------|-------|
| 1. Learning objectives | PASS | 4 clear, measurable items |
| 2. Prerequisite activation | PASS | References OLS from prior lectures explicitly |
| 3. Motivation before theory | PASS | Binary Y examples (buy/sell, mortgage) precede formalization |
| 4. Worked examples | PASS | Multiple: P/I table, HMDA calculations, discrimination estimates |
| 5. Progressive disclosure | PASS | Fragment-based reveals used consistently |
| 6. Comprehension checks | **FAIL** | No `.question` or `.poll` slides in entire deck |
| 7. Notation consistency | PASS | $Y_i$, $X_i$, $Pr(\cdot)$, $\hat{P}$ consistent throughout |
| 8. Real-world anchoring | PASS | HMDA dataset provides strong motivating case |
| 9. Summary/closing | PASS | Two-column pros/cons summary slide |
| 10. Forward bridge | PASS | Last slide previews Probit/Logit |
| 11. Pacing | PASS | 26 slides, well-distributed |
| 12. Difficulty ramp | PASS | Starts intuitive, ends with caveats |
| 13. Active learning | **WEAK** | No exercises; no student practice opportunity |

---

## Issues Found

### MEDIUM

**P1 — No comprehension checks**
- The deck has zero `.question` or `.poll` slides. The HMDA dataset provides a natural stopping point for a comprehension check after the "LPM simples" slide.
- **Recommendation:** Add one `.question` callout after the "LPM com raça" slide, e.g.:
  > "Um branco com P/I = 0,20 e um preto com P/I = 0,20: qual a diferença na probabilidade prevista de negação? Calcule."

**P2 — No active learning exercise**
- Across 26 slides, students never practice. Given the HMDA data is rich and the calculations are tractable, a brief `.appex` exercise would reinforce learning.
- **Recommendation:** Add a one-slide `.appex` exercise after the full-controls table (line 369), asking students to interpret the `black` coefficient in context.

### LOW

**P3 — "Limitação 1 de 3" / "Limitação 2 de 3" labels in r-stack**
- The current-visible pattern hides the first two limitation descriptions once the summary appears. The labels are useful during the transitions but disappear. Students reviewing slides asynchronously will only see the summary.
- **Recommendation:** No action required if live-lecture use is primary. For asynchronous review, the final summary slide covers all three points adequately.

**P4 — $R^2$ failure explanation**
- The slide "Por que o $R^2$ falha" (line 186) is well-designed. One minor improvement: mentioning that pseudo-$R^2$ will be covered "na próxima aula" is already done (line 203) — good cross-lecture bridging.

---

## Strengths

1. HMDA discrimination case is a compelling real-world application that maintains student interest through the technical material.
2. The "Quando o LPM é suficiente?" slide (line 482) with the Angrist & Pischke recommendation is excellent — gives students a practical framework.
3. The `r-stack` on discrimination data (line 229) — showing raw statistics, then raising the question, then showing the omitted variable problem — is pedagogically sophisticated.
4. The heterocedasticidade table (line 465) with intuitive "evento raro / máxima incerteza" column is a strong visual aid.

---

## Overall Pedagogical Assessment

**Rating: GOOD** — Strong narrative, well-anchored in real data, appropriate pacing. Main gap is absence of comprehension checks and exercises.
