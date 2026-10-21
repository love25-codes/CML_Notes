# 16 — Final Recap

## Three things learned

### 1. Ridge, Lasso, and Elastic Net

- Ridge → L2
- Lasso → L1
- Elastic Net → L1 + L2

### 2. L1 vs L2 geometry

- L2 → smooth circular constraint → smooth coefficient shrinking.
- L1 → diamond-like constraint with corners → coefficients can become exactly zero.

### 3. K-Fold Cross-Validation without leakage

Use folds to get multiple validation measurements.

Keep learned preprocessing inside the Pipeline so validation information does not leak into training.

## Two things to remember

### Remember 1

$$
X^TX+\lambda I
$$

Ridge's $\lambda I$ term helps repair the multicollinearity / singular-matrix problem described in the session.

### Remember 2

Report:

$$
\text{CV mean} \pm \text{CV standard deviation}
$$

The spread across folds is meaningful.

## One thing to think about

Regularization fights variance by adding a penalty.

The session ends by asking another question:

> Could variance instead be reduced by averaging many models?

That leads to the idea of **ensemble methods**, which the session identifies as a later topic.
