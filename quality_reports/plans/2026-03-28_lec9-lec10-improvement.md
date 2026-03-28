---
status: APPROVED
date: 2026-03-28
files: slides/lec-9.qmd, slides/lec-10.qmd
---

# Plan: Improve lec-9 and lec-10 (Variável Dependente Limitada)

## Goals
- Fix all text overflow (min font 60%, fix width="150%" bug)
- Add r-stack + fragments for more dynamic reveals
- Extract and use S&W Table 11.1 and Table 11.2

## lec-9 Changes
1. Fix typo: "dependennte" → "dependente"
2. Add `.fragment` to sub-bullets in "Variável Dependente Binária"
3. Add fragments to "Regressão quando Y é binária" (bullets 2 and 3)
4. Add fragments to "Modelo de Probabilidade Linear" (equations)
5. Add fragments to "LPM: estimação e inferência"
6. Add fragments to "LPM: identificação" (hypothesis list)
7. Use r-stack in "Existe discriminação racial?" for progressive reveal
8. NEW SLIDE: "Variáveis disponíveis: dados HMDA" with Table 11.1 image
9. Replace overflowing image equation with LaTeX (eq 11.3)
10. Use r-stack for "Limitações do LPM" (show limitations one at a time)

## lec-10 Changes
1. Add fragments to "Introdução aos modelos não lineares"
2. Add fragments to "Função de Distribuição Acumulada"
3. Add fragments to "Interpretação de coeficientes" (3-step process)
4. Restructure "MLE: formalização" with fragments
5. Add fragments to "Propriedades do estimador MLE"
6. Fix "Erros-padrão e inferência" formatting
7. Enhance "Medidas de ajuste" with definitions and fragments
8. REPLACE external link slide with Table 11.2 image + new interpretation slide
9. Add fragments to "Angrist & Pischke" slide
10. Fix typo "errros-padrão" → "erros-padrão" in "Guia Prático"

## Images Extracted
- slides/images/lec-9/stock_watson_tab_11_1.png (Table 11.1, PDF page 409)
- slides/images/lec-10/stock_watson_tab_11_2.png (Table 11.2, PDF page 411)
