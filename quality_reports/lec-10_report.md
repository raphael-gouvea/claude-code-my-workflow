# Proofreading Report: lec-10.qmd
**Date:** 2026-03-29
**Reviewer:** proofreader (Agent 3)

## Summary

| Severity | Count |
|----------|-------|
| Critical | 0 |
| Medium   | 3 |
| Low      | 3 |

---

## Issues Found

### MEDIUM

**G1 — Ordinal indicators missing (lines 46, 48)**
- Same issue as lec-9: "1a Edição" → "1ª Edição"; "4a Edição" → "4ª Edição".
- **Fix:** Same as lec-9 G1.

**G2 — Numerical error in log-likelihood calculation (line 406)**
- Slide "Pseudo-$R^2$: interpretação e cálculo" states:
  > `$\ln L_{\text{nulo}} \approx 2380[0{,}12\ln(0{,}12) + 0{,}88\ln(0{,}88)] \approx 2380(-0{,}273) \approx -650$`
- **Verification:**
  - $0.12 \times \ln(0.12) = 0.12 \times (-2.120) = -0.2544$
  - $0.88 \times \ln(0.88) = 0.88 \times (-0.1278) = -0.1125$
  - Sum: $-0.3669$
  - $2380 \times (-0.3669) = -873$
- The slide writes $-0.273$ for the bracket (incorrect; correct is $-0.367$) and arrives at $-650$ (should be approximately $-873$).
- **Consequence:** The pseudo-$R^2$ example calculation on line 410 is also affected: `$R^2_{MF} = 1 - (-500)/(-650) = 0.231$` should use $-873$ in the denominator if $-500$ is the model log-likelihood.
- **Fix:** Correct the intermediate value from $-0{,}273$ to $-0{,}367$ and the final value from $-650$ to $-873$. Update the pseudo-$R^2$ calculation accordingly.

**G3 — Logit coefficient scaling factor imprecise (lines 449, 457)**
- Line 449 table: "Maiores ($\approx 1{,}6\times$)"
- Line 457: "$\sqrt{3{,}29} \approx 1{,}6$ vezes maiores"
- **Verification:** $\sqrt{\pi^2/3} = \pi/\sqrt{3} \approx 1.814$, not 1.6. The approximate rule-of-thumb "1.6" exists in some textbooks (Amemiya 1981 suggests multiplying probit by 1.6–1.7), but the slide presents this as a calculation from $\sqrt{3.29}$, which gives 1.81, not 1.6. This is internally inconsistent.
- **Fix:** Either (a) change the table to "$\approx 1{,}8\times$" and the text to "$\sqrt{3{,}29} \approx 1{,}81$", or (b) keep "1.6" as an Amemiya rule-of-thumb but cite it as such: "pela regra prática de Amemiya (1981), $\approx 1{,}6$" and remove the $\sqrt{3.29}$ calculation that contradicts it.

### LOW

**L1 — Same ordinal issue in references as lec-9**
- Already captured in G1.

**L2 — Citation reference consistency (same issue as lec-9)**
- Line 465: "Fonte: @stock_watson_2004, Table 11.2." — English edition citation. Consistent with lec-9 pattern.
- **Recommendation:** Same as lec-9 L4 — clarify which edition equation numbers refer to.

**L3 — Callout title duplication ("Guia Prático")**
- Line 543 slide title: "Guia Prático" — and callout title (line 544): "## Guia Prático". Redundant.
- **Fix:** Change callout title to "Prática recomendada" or remove the outer callout wrapper.

---

## Mathematical Content Verification

| Slide | Calculation | Result | Verified |
|-------|-------------|--------|---------|
| Probit P/I=0.2 | $\Phi(-1.60) = 5.5\%$ | ✓ | PASS |
| Probit P/I=0.3 | $\Phi(-1.30) = 9.7\%$ | ✓ | PASS |
| Probit P/I=0.4 | $\Phi(-1.00) = 15.9\%$ | ✓ | PASS |
| Probit P/I=0.6 | $\Phi(-0.40) = 34.5\%$ | ✓ | PASS |
| Probit with race | White: $\Phi(-1.44) = 7.5\%$ | ✓ | PASS |
| Probit with race | Black: $\Phi(-0.73) = 23.3\%$ | ✓ | PASS |
| Logit with race | White: $\Lambda(-2.52) = 7.4\%$ | ✓ | PASS |
| Logit with race | Black: $\Lambda(-1.25) = 22.3\%$ | ✓ | PASS |
| Marginal effects table | All three rows | ✓ | PASS |
| McFadden pseudo-R² | Intermediate value | **FAIL** (see G2) | FAIL |
| Logit scaling | $\sqrt{3.29} \approx 1.81 \neq 1.6$ | **FAIL** (see G3) | FAIL |

---

## Writing Quality

- Academic register maintained. PASS.
- Portuguese grammar correct. PASS.
- Consistent terminology across lec-9 and lec-10. PASS.
- No typos detected.
