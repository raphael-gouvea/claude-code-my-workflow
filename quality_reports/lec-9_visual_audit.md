# Visual Audit: lec-9.qmd
**Date:** 2026-03-29
**Auditor:** slide-auditor (Agent 1)

## Summary

| Severity | Count |
|----------|-------|
| Critical | 0 |
| Medium   | 2 |
| Low      | 3 |

---

## Issues Found

### MEDIUM

**M1 — Table overflow risk (slide "Exemplo Prático: Calculando Probabilidades Previstas")**
- Line 164–170: The third table column contains inline math + text mixed content: `$7{,}7\% + 17{,}7\;\text{p.p.} = 25{,}4\%$`. At 86% font this is borderline. On narrower screens the column may overflow or wrap awkwardly.
- **Recommendation:** Simplify the third cell to just `25,4%` and add the calculation as a footnote or bullet below the table.

**M2 — Image without explicit width (slide "Relação entre P/I ratio e negação do empréstimo")**
- Line 314: `![](images/lec-9/stock_watson_fig_11_1.png)` — no width attribute. In a two-column layout, the image will fill the right column fully but may look disproportionate relative to the text-heavy left column.
- **Recommendation:** Add `{width="90%"}` for visual balance with the text column.

### LOW

**L1 — Box fatigue: callout frequency**
- 3 callout boxes in 26 slides: `.callout-tip` (×2) and `.callout-important` (×1). Acceptable but nearing the threshold. No changes required.

**L2 — `r-stack` limitation labels ("Limitação 1 de 3", "Limitação 2 de 3")**
- Lines 418–445: The first two `.current-visible` fragments vanish after the summary panel appears. The "1 de 3 / 2 de 3" labels are useful while reading, but since only the summary remains visible, students who miss the transition won't see which limitation is which.
- **Recommendation:** Consider adding a brief label in the summary fragment (e.g., bold "1.", "2.", "3." before each item in the final list) — already partially done via the numbered list. No changes required.

**L3 — `stock_watson_tab_11_1.png` image scale**
- Line 271: `width="85%"` — fine for most screens. No issue.

---

## Layout Compliance

| Check | Status |
|-------|--------|
| Fragment reveals used consistently | PASS |
| `r-stack` / `.current-visible` patterns correct | PASS |
| Font sizes consistent (85–90% range) | PASS |
| Tables have headers | PASS |
| Images have source attribution | PASS |
| No TikZ present | N/A |
