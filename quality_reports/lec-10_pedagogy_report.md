# Pedagogical Review: lec-10.qmd
**Date:** 2026-03-29
**Reviewer:** pedagogy-reviewer (Agent 2)
**Topic:** Variável Dependente Binária — Probit e Logit

## Narrative Arc Assessment

**Structure:** Why not LPM alone → CDF concept → Probit → Logit → Non-linearity of effects → Why not OLS for Probit/Logit → MLE intuition → MLE formalization → properties → inference → fit measures → identification continuity → comparison → practical guidance → "regra de ouro."

The arc is logical and builds carefully on lec-9. The decision to move from intuition (videos) to formalization (likelihood function) to properties is pedagogically sound.

**Pacing:** 26 slides — appropriate. The MLE section (slides 13–17) is the densest and may benefit from one bridging slide.

---

## 13 Pedagogical Patterns Checklist

| Pattern | Status | Notes |
|---------|--------|-------|
| 1. Learning objectives | PASS | 4 items; specific and measurable |
| 2. Prerequisite activation | PASS | References lec-9 LPM limitations as motivation |
| 3. Motivation before theory | PASS | "Introdução aos modelos não lineares" frames the need for CDF |
| 4. Worked examples | PASS | Probit + Logit calculations, MLE numerical example, McFadden example |
| 5. Progressive disclosure | PASS | Fragment reveals consistent |
| 6. Comprehension checks | **FAIL** | No `.question` or `.poll` slides |
| 7. Notation | PASS | $\Phi$, $\Lambda$, $F(\cdot)$ consistently differentiated |
| 8. Real-world anchoring | PASS | HMDA continuation + probit-decline chart |
| 9. Summary/closing | PASS | "Qual modelo usar?" numbered guide is excellent |
| 10. Forward bridge | WEAK | No explicit bridge to next lecture (lec-11 on IV) |
| 11. Pacing | PASS | 26 slides, well-distributed |
| 12. Difficulty ramp | PASS | MLE hardest section; well-positioned late in deck |
| 13. Active learning | **WEAK** | No exercises |

---

## Issues Found

### MEDIUM

**P1 — No comprehension checks (same gap as lec-9)**
- Natural stopping point: after "Efeitos Marginais" table, ask students to calculate the marginal effect for a different interval.
- **Recommendation:** Add one `.question` after the marginal effects table (line 228):
  > "Com o modelo probit simples, qual é o efeito marginal para a mudança de P/I = 0,60 para 0,70?"

**P2 — YouTube video slide lacks pedagogical scaffolding**
- Lines 267–277: Two YouTube videos are shown without guiding questions or learning objectives for the videos.
- **Recommendation:** Add 2–3 bullet points below the videos: "Ao assistir, preste atenção em: (1) o que significa maximizar a verossimilhança, (2) a diferença entre MQO e MV."

**P3 — MQNL mention adds confusion**
- Line 261: "Alternativa: Mínimos Quadrados Não Lineares (MQNL) — consistente, mas não eficiente." This term is introduced but never developed. Students who aren't familiar may fixate on it.
- **Recommendation:** Remove the MQNL bullet or replace with: "Alternativa: estimação por distância — menos eficiente e menos comum na prática."

### LOW

**P4 — No forward bridge to lec-11**
- The deck ends with a strong "regra de ouro" (identification > functional form), but makes no connection to upcoming Instrumental Variables content.
- **Recommendation:** On the summary slide, add a closing sentence: "→ Na próxima aula: **Variáveis Instrumentais** — quando a exogeneidade falha."

**P5 — Logit difference from Probit unexplained**
- Line 479–483: The table shows Logit estimates +6.0 p.p. vs. Probit +7.1 p.p. — a meaningful difference that could confuse students. No explanation is given for why the numbers differ.
- **Recommendation:** Add a brief parenthetical: "(diferença devida à escala distinta das distribuições; ambas são estimativas válidas do efeito médio)."

---

## Strengths

1. "Qual modelo usar?" (numbered 1–5, line 552) is the best practical guide in the course so far — clear, actionable, hierarchical.
2. The probit-decline chart (line 578) is a powerful empirical observation that motivates the Angrist & Pischke view. Excellent evidence-based pedagogy.
3. The comparison table Probit vs. Logit (line 441) is comprehensive and well-formatted.
4. MLE intuition slide with numerical example before the formal likelihood function — the right order.
5. "Identificação: os mesmos problemas do LPM se aplicam" (line 420) correctly emphasizes that functional form ≠ identification strategy.

---

## Overall Pedagogical Assessment

**Rating: GOOD** — Strong conceptual flow, excellent practical guidance, well-anchored in real data. Main gaps: no comprehension checks, video slide needs scaffolding, no forward bridge.
