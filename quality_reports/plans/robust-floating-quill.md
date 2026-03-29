# Plan: Significant Expansion of Lec-9 and Lec-10 (Variável Dependente Limitada)

**Status:** DRAFT
**Date:** 2026-03-29
**Scope:** Significant expansion (~10 new slides per lecture + enrich existing)
**Reference:** Stock & Watson (2020), Chapter 11

---

## Context

Lec-9 and Lec-10 were migrated from older content. They are structurally sound but thin on depth: few numerical examples, no worked computations, missing key S&W material (R² failure, marginal effects, pseudo-R², full regression table, identification for nonlinear models). The user now wants full S&W Chapter 11 coverage across both lectures.

---

## Files to Modify

- `slides/lec-9.qmd` — LPM lecture
- `slides/lec-10.qmd` — Probit/Logit lecture

---

## Lec-9 Expansion Plan

### Enrich existing slides
- **Bernoulli slide:** Add Var(Y) = p(1-p) and connect to heteroskedasticity formula later.
- **LPM coefficient slide:** Add the full S&W Eq. (11.1) with SEs and t-statistic. Add numerical example: "If P/I = 0.25, predicted deny = -0.091 + 0.559(0.25) = 0.049 = 4.9%."
- **Limitations slide (out-of-[0,1]):** Add the Figure 11.1 reference (scatterplot showing LPM line going negative).
- **Heteroskedasticity slide:** Expand with variance formula Var(u|X) = P(1-P), show it peaks at P=0.5 and collapses to 0 at extremes. Add a small table or graph of this shape.

### New slides to add (~10)

1. **Predicted Probabilities — Worked Example (after coefficient interpretation)**
   Step-by-step: plug P/I = 0.25 and P/I = 0.45 into the LPM equation. Show the difference = estimated effect. Reinforce: effect is constant across all X values (limitation of linearity).

2. **Why R² Fails for Binary Y**
   All observations sit on two horizontal lines (y=0 and y=1). Standard R² compares residuals to mean, but mean of binary Y is not a meaningful center. Show intuition with a simple diagram description. Recommend: use fraction correctly predicted instead (preview for Lec-10).

3. **Heteroskedasticity: Visualization and Intuition**
   Show Var(u|X) = P(1-P) graphically: variance is zero when P=0 or P=1 (no uncertainty), maximum at P=0.5 (maximum uncertainty). Consequence: OLS SEs are invalid without HC correction.

4. **Boston HMDA: Dataset Description**
   Table 11.1 variables: P/I ratio, housing expense ratio, loan-to-value, consumer credit score, mortgage credit score, public bad credit, race indicator, denial outcome. N=2,380 Boston applications, 1990. Overall denial rate: 12%.

5. **Boston HMDA: LPM with Financial Controls (Table 11.2, Col. 1)**
   Key results: P/I +0.449 (SE 0.114), loan-to-value high +0.189, consumer credit score +0.031, bad credit record +0.197. All significant. Sets up the causal question about race.

6. **Boston HMDA: Adding Race as Regressor (Eq. 11.3)**
   Expand current slide: add SEs, t-statistic (t = 7.11), confidence interval. Compute: a Black applicant with P/I = 0.3 faces Pr = 9% vs. 26.6% for a white applicant with same P/I. Economically and statistically significant.

7. **Internal Validity Threats**
   Three caveats from S&W p. 412: (1) unobserved in-person interview quality correlated with race; (2) alternative functional forms; (3) external validity (Boston 1990 vs. today). Motivates robustness checks.

8. **When Is LPM Adequate?**
   If predicted probabilities stay far from 0 and 1, LPM ≈ Probit/Logit. Angrist & Pischke recommendation: always report LPM with robust SEs, add Probit/Logit as robustness. Causal identification is what matters, not functional form.

9. **LPM Summary: Pros and Cons**
   Pro: simple, easy to interpret, all OLS tools apply, works with IV and FE.
   Con: predictions outside [0,1], inherent heteroskedasticity, ignores nonlinearity.
   Bridge: motivates nonlinear alternatives (Probit, Logit) in next lecture.

---

## Lec-10 Expansion Plan

### Enrich existing slides
- **Probit model slide:** Add S&W Key Concept 11.2. Add step-by-step numerical example with actual S&W numbers: β₀ = -2.19, β₁ = 2.97. Compute denial probabilities at P/I = 0.3, 0.4, 0.5.
- **Logit model slide:** Add logistic CDF formula Λ(z) = 1/(1+e^{-z}) and explain why it's convenient (closed-form, unlike Φ). Add S&W Key Concept 11.3.
- **Marginal effects slide:** Expand 3-step procedure with actual numbers. Show that same ΔX = 0.1 gives 6.2 p.p. at P/I 0.3→0.4 vs. 8.0 p.p. at P/I 0.4→0.5. Make nonlinearity concrete.
- **MLE slide:** Add intuition: "MLE finds parameters that make observed data most likely. For Yᵢ=1 we want Pᵢ large; for Yᵢ=0 we want Pᵢ small."
- **Practical guidance slide:** Strengthen with Angrist & Pischke quote + explicit recommendation.

### New slides to add (~10)

1. **Why Not OLS for Probit? (before MLE)**
   OLS minimizes sum of squared residuals, which works when model is linear in parameters. Probit/Logit are nonlinear in β — gradient-based OLS minimization fails. Need MLE (or nonlinear least squares, but MLE is efficient).

2. **MLE Worked Intuition**
   Simple example: one observation, Y=1, model predicts P=0.8. Contribution to likelihood = 0.8. Another: Y=0, P=0.3. Contribution = 0.7 = 1-0.3. MLE maximizes product of all such contributions. Log-likelihood avoids numerical underflow.

3. **MLE: Log-Likelihood Formula**
   ln L(β) = Σᵢ [Yᵢ ln Pᵢ + (1-Yᵢ) ln(1-Pᵢ)]. Show that this is maximized numerically (Newton-Raphson). Software does this automatically. Estimated β̂ are consistent, asymptotically normal, efficient.

4. **Standard Errors in Probit/Logit**
   SE from Fisher information matrix (Hessian of log-likelihood). Inference: z-test = β̂/SE (asymptotically N(0,1)). CIs: β̂ ± 1.96·SE. Joint tests: Likelihood Ratio Test (compare log-likelihoods of restricted vs. unrestricted model).

5. **Measures of Fit: Pseudo-R² and Fraction Correctly Predicted**
   McFadden Pseudo-R² = 1 - ln(L_model)/ln(L_null). Ranges 0–1 but values are not comparable to OLS R². Rule of thumb: >0.2 is good. Fraction correctly predicted: count Ŷ ≥ 0.5 and Y=1 as correct, Ŷ < 0.5 and Y=0 as correct. Limitation: doesn't distinguish confidence (Ŷ=0.51 vs. Ŷ=0.99 both count).

6. **Identification: Same Issues as LPM Apply**
   OVB, selection bias, measurement error all apply to Probit/Logit. Nonlinear functional form does NOT solve identification. The choice of F (Φ or Λ) is secondary to identifying assumptions. Bad identification cannot be fixed by nonlinearity.

7. **Probit vs. Logit: Practical Differences**
   Logit coefficients ≈ 1.6 × Probit coefficients (scaling due to variance of distributions). Predicted probabilities nearly identical for moderate P values. Logit preferred in practice (closed-form, easier optimization). Probit retains interpretability via standard normal table.

8. **Full Comparison Table: LPM, Probit, Logit (Table 11.2)**
   Boston HMDA results for Black indicator: LPM → +8.4 p.p., Logit → +6.0 p.p., Probit → +7.1 p.p. All significant at 1%. All models agree qualitatively. Marginal quantitative differences.

9. **Robustness Across Specifications**
   S&W Table 11.2 columns (4)-(6): add education, marital status, unemployment, property type. Black coefficient stays large and significant (6.5–7.1 p.p.). Omitted variable bias from excluded controls is modest.

10. **Summary: Which Model to Use?**
    Decision tree: (1) Is causal identification clean? If not, no model helps. (2) If yes: report LPM + robust SEs as baseline. (3) Add Probit or Logit as robustness check. (4) If predictions outside [0,1] are a concern, prefer Probit/Logit. Core message: identification > functional form.

---

## Execution Order

1. Enhance `slides/lec-9.qmd` (read current state → enrich existing → insert new slides in logical positions)
2. Verify lec-9 compiles (`quarto render slides/lec-9.qmd`)
3. Enhance `slides/lec-10.qmd` (same approach)
4. Verify lec-10 compiles (`quarto render slides/lec-10.qmd`)
5. Run quality score on both: `python scripts/quality_score.py slides/lec-9.qmd` and `lec-10.qmd`
6. Run `/slide-excellence` on both if quality < 90

---

## Verification

- Both files render without errors
- Quality score ≥ 90/100 for each lecture
- New numerical examples match S&W equations exactly
- Slide count increases: lec-9 by ~9 slides, lec-10 by ~10 slides
- All new content is in Portuguese (course language)
