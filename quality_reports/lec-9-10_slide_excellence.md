# Slide Excellence Review: lec-9.qmd + lec-10.qmd
**Date:** 2026-03-29
**Files:** `slides/lec-9.qmd`, `slides/lec-10.qmd`
**Topic:** Variável Dependente Limitada (1) e (2)

---

## Overall Quality Scores

| File | Visual | Pedagogy | Proofreading | **Overall** |
|------|--------|----------|--------------|-------------|
| lec-9.qmd | GOOD | GOOD | GOOD | **GOOD (85/100)** |
| lec-10.qmd | GOOD | GOOD | NEEDS WORK | **GOOD (82/100)** |

---

## Dimension Summary

### lec-9.qmd

| Dimension | Critical | Medium | Low |
|-----------|----------|--------|-----|
| Visual/Layout | 0 | 2 | 3 |
| Pedagogical | 0 | 2 | 2 |
| Proofreading | 0 | 2 | 4 |
| **Total** | **0** | **6** | **9** |

### lec-10.qmd

| Dimension | Critical | Medium | Low |
|-----------|----------|--------|-----|
| Visual/Layout | 0 | 3 | 3 |
| Pedagogical | 0 | 3 | 2 |
| Proofreading | 0 | 3 | 3 |
| **Total** | **0** | **9** | **8** |

---

## Critical Issues (Immediate Action Required)

**None.** Both decks are free of critical errors. All mathematical content in lec-9 is correct. Lec-10 has two medium-severity mathematical errors.

---

## Medium Issues (Next Revision)

### Both Files

**[BOTH-M1] Ordinal indicators**
- `1a Edição` → `1ª Edição`; `4a Edição` → `4ª Edição` in the References slide of both lec-9 and lec-10.
- **Files:** lec-9.qmd lines 46/48; lec-10.qmd lines 46/48.

**[BOTH-M2] No comprehension checks**
- Neither deck has a `.question` or `.poll` slide. Two lectures with no student interaction point is a pedagogical gap.
- **Recommendation:** Add 1 `.question` slide per lecture.

### lec-9.qmd Only

**[9-M1] ASCII `...` in math mode**
- Replace all `...` with `\ldots` in equations (lines 96, 103, 113, 117, 129, 130).
- LaTeX renders these with incorrect spacing in math mode.

**[9-M2] Table overflow risk**
- "Exemplo Prático" table (line 164): third column has mixed text+math that may overflow.
- Simplify the third cell or reduce font size to 80%.

### lec-10.qmd Only

**[10-M1] Numerical error in McFadden pseudo-R² calculation**
- Line 406: The bracket value $-0{,}273$ is incorrect; should be $-0{,}367$.
- The null log-likelihood is $\approx -873$, not $\approx -650$.
- The pseudo-R² calculation on line 410 must be updated accordingly.
- **This is a factual error that should be fixed before use.**

**[10-M2] Logit scaling factor internally inconsistent**
- Line 457: `$\sqrt{3{,}29} \approx 1{,}6$` — $\sqrt{3.29} = 1.81 \neq 1.6$.
- Either correct the numeric value to $\approx 1{,}81$, or remove the calculation and cite Amemiya (1981) rule-of-thumb.

**[10-M3] "Angrist & Pischke" slide: 72% font**
- Too small for classroom readability. Increase to 78% or split the slide.

**[10-M4] YouTube video slide lacks scaffolding**
- Add guiding questions below the two videos.

---

## Low-Priority Issues

### lec-9.qmd
- **[9-L1]** Interval notation `;;` (line 488) → use `;\,`
- **[9-L2]** Image width missing on figure 11.1 (line 314) → add `{width="90%"}`
- **[9-L3]** "variáveis dummies" — acceptable anglicism in Brazilian econometrics, no change required

### lec-10.qmd
- **[10-L1]** Images in column layouts lack `{width="100%"}` (lines 93, 122, 175)
- **[10-L2]** Callout title duplication "Guia Prático" (line 543) → rename callout title
- **[10-L3]** 40% font for source attribution (line 582) → increase to 60%
- **[10-L4]** No forward bridge to lec-11 at end of deck → add one sentence

---

## Recommended Fix Order

### Immediate (before next class)

1. **[10-M1]** Fix McFadden log-likelihood calculation (numerical error, students may reproduce it)
2. **[10-M2]** Fix $\sqrt{3.29} \approx 1.6$ → $\approx 1.81$ (internal inconsistency)
3. **[BOTH-M1]** Fix ordinal indicators `1a` → `1ª` in both files
4. **[9-M1]** Replace `...` with `\ldots` in lec-9 equations

### Next Revision

5. **[BOTH-M2]** Add 1 comprehension check per lecture
6. **[10-M3]** Increase "Angrist & Pischke" font from 72% to 78%
7. **[10-M4]** Add scaffolding to video slide
8. **[9-M2]** Simplify table third column in "Exemplo Prático"

### Optional Polish

9. **[10-L1]** Add `{width="100%"}` to column images in lec-10
10. **[10-L4]** Add forward bridge to lec-11
11. **[10-L2]** Fix callout title duplication
12. **[10-L3]** Increase attribution font from 40% to 60%
13. **[9-L1]** Fix interval notation
14. **[9-L2]** Add image width to figure 11.1

---

## Agent Reports (Saved)

| Agent | lec-9 | lec-10 |
|-------|-------|--------|
| Visual Audit | `quality_reports/lec-9_visual_audit.md` | `quality_reports/lec-10_visual_audit.md` |
| Pedagogical Review | `quality_reports/lec-9_pedagogy_report.md` | `quality_reports/lec-10_pedagogy_report.md` |
| Proofreading | `quality_reports/lec-9_report.md` | `quality_reports/lec-10_report.md` |
