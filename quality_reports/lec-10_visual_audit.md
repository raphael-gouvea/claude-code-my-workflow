# Visual Audit: lec-10.qmd
**Date:** 2026-03-29
**Auditor:** slide-auditor (Agent 1)

## Summary

| Severity | Count |
|----------|-------|
| Critical | 0 |
| Medium   | 3 |
| Low      | 3 |

---

## Issues Found

### MEDIUM

**M1 — Images without explicit widths in two-column layouts**
- Line 93–96 ("CDF e PDF"): Two `![](...)` images side by side, no `{width=}` attributes.
- Line 122–124 ("Modelo Probit"): Right-column image `stock_watson_fig_11_2.png` has no width.
- Line 175–177 ("Modelo Logit"): Right-column image `stock_watson_fig_11_3.png` has no width.
- **Recommendation:** Add `{width="100%"}` to all column images for predictable rendering.

**M2 — Oversized callout density in lec-10**
- 3 `.callout-tip` and 3 `.callout-important` in 26 slides = 6 callout boxes.
- The two `.callout-important` on slides "Discriminação racial: interpretação" and "Resumo: qual modelo usar?" appear within 4 slides of each other, creating visual monotony.
- **Recommendation:** Consider downgrading "Conclusão" callout on slide 18 to a styled blockquote or plain bold text, reserving `.callout-important` for the "Regra de ouro" on slide 22.

**M3 — "Angrist & Pischke" slide: 72% font**
- Line 523: `{style="font-size: 72%;"}` — this is below the 75% minimum for classroom readability from the back of a room. Text at this size will likely be illegible for students seated more than 5m from the screen.
- **Recommendation:** Increase to 78% or split the slide into two.

### LOW

**L1 — YouTube video slide: no offline fallback**
- Line 267–277 ("Estimação por MV: intuição"): Two embedded `{{< video ... >}}` YouTube embeds. If internet is unavailable in the classroom, this slide is empty.
- **Recommendation:** Add a brief text note below the videos (e.g., "Vídeos disponíveis no link da aula no Moodle") as fallback.

**L2 — 40% font for image attribution**
- Line 582: `{style="font-size: 40%;"}` — barely visible. Standard practice is 60–65% for attributions.
- **Recommendation:** Increase to 60%.

**L3 — Callout title redundancy ("Guia Prático" slide)**
- Lines 543–550: `.callout-tip` has title "Guia Prático" and the slide header is also "Guia Prático". Duplicated heading at different levels.
- **Recommendation:** Change the callout title to a more specific label, e.g., "Prática recomendada" or remove the callout wrapper and use plain text.

---

## Layout Compliance

| Check | Status |
|-------|--------|
| Fragment reveals used consistently | PASS |
| `r-stack` pattern correct | PASS |
| Font sizes (except M3 and L2 above) | PASS |
| Tables have headers | PASS |
| Images have source attribution | PASS |
| No TikZ present | N/A |
