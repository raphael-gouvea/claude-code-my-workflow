# Proofreading Report: lec-9.qmd
**Date:** 2026-03-29
**Reviewer:** proofreader (Agent 3)

## Summary

| Severity | Count |
|----------|-------|
| Critical | 0 |
| Medium   | 2 |
| Low      | 4 |

---

## Issues Found

### MEDIUM

**G1 — Ordinal indicators missing feminine superscript (lines 46, 48)**
- "1a Edição" and "4a Edição" should use the feminine ordinal indicator: "1ª Edição" and "4ª Edição".
- In Quarto markdown: use `1ª` (HTML entity) or the Unicode character `ª`.
- **Fix:** Change `1a Edição` → `1ª Edição` and `4a Edição` → `4ª Edição`.

**G2 — ASCII ellipsis instead of LaTeX `\ldots` (lines 96, 103, 113, 117, 129, 130)**
- Multiple equations use `...` (three ASCII periods) inside math mode. LaTeX renders these as separate dots with awkward spacing.
- Example line 96: `E(Y \mid X_1,X_2,...,X_k)` → should be `E(Y \mid X_1,X_2,\ldots,X_k)`.
- Affects lines 96, 103, 113, 117, 129, 130.
- **Fix:** Replace all `...` inside math delimiters with `\ldots`.

### LOW

**L1 — Interval notation `;;` (line 488)**
- `$\hat{P}_i \in [0{,}1\;;\;0{,}9]$` uses a double semicolon as separator inside an interval. Standard notation in Portuguese econometrics would use a semicolon or comma: `[0{,}1;\,0{,}9]` or simply state the range in words.
- **Fix:** Change `[0{,}1\;;\;0{,}9]` to `[0{,}1;\,0{,}9]`.

**L2 — "dummies" anglicism (line 62)**
- "variáveis dummies" — while commonly used in Brazilian econometric pedagogy, the Portuguese "variáveis binárias" or "variáveis indicadoras" is preferable for consistency with the rest of the slides.
- **Severity:** Low — this is conventional usage in the field. No required change, but flag for instructor preference.

**L3 — Missing period in callout body (line 504)**
- The `.callout-tip` body ends with "adicione Probit ou Logit como verificação de robustez." — correct punctuation is present. **No issue — reviewed and PASS.**

**L4 — Citation reference consistency**
- Line 151: "S&W Eq. 11.3" — this equation appears in the English 4th edition. The Portuguese 1st edition uses different chapter numbering (Chapter 9 vs Chapter 11). Consider adding a note clarifying which edition the equation numbers refer to, since both are listed as references.
- **Recommendation:** Standardize to one notation, e.g., "(S&W, Eq. 11.3 — edição inglesa)" when citing English-only numbering.

---

## Mathematical Content Verification

All numerical calculations in lec-9 checked and verified:

| Slide | Calculation | Result | Verified |
|-------|-------------|--------|---------|
| LPM simples | $-0.080 + 0.604(0.20) = 4.1\%$ | ✓ | PASS |
| LPM simples | $-0.080 + 0.604(0.50) = 22.2\%$ | ✓ | PASS |
| LPM com raça | White P/I=0.30: 7.7% | ✓ | PASS |
| LPM com raça | Black P/I=0.30: 25.4% | ✓ | PASS |
| Exemplo prático | All three rows | ✓ | PASS |
| Heteroc. table | $P=0.5 \Rightarrow \text{Var}=0.25$ | ✓ | PASS |

---

## Writing Quality

- Academic register maintained throughout. PASS.
- Portuguese grammar is correct. PASS.
- Terminology consistent with S&W Portuguese edition conventions. PASS.
- No typos detected.
