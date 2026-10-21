# 2. Correlation and the Variance Floor

## Formula from the session

\[
\\mathrm{Var}(\\bar f)=\\rho\\sigma^2+\\frac{1-\\rho}{B}\\sigma^2
\]

Where:
- `B` = number of models in the ensemble.
- `σ²` = variance of one model.
- `ρ` = pairwise correlation between models.

## Read the formula simply
There are two parts:

1. **Correlation floor:** `ρσ²`. This part does not shrink just because we add more models.
2. **Reducible part:** `((1 − ρ) / B)σ²`. This part gets smaller as `B` increases.

That means adding more trees eventually gives diminishing benefits if the trees are strongly correlated.

## Two extreme cases
- If `ρ = 0`, the models are uncorrelated in this formula, and variance becomes `σ² / B`.
- If `ρ = 1`, all models are perfectly correlated, and averaging leaves variance at `σ²`.

## Worked example
Suppose `σ² = 1`, `ρ = 0.2`, and `B = 100`.

\[
0.2(1)+\\frac{1-0.2}{100}(1)=0.2+0.008=0.208
\]

The variance falls from `1` to `0.208` (about `0.21`). The `0.2` correlation floor remains.

## Remember
Reducing correlation can matter as much as increasing the number of models. Random Forest is designed to reduce this correlation.
