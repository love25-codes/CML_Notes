# 05 — Two Rules and Two Extremes of Ridge

## Rule 1 — Always scale first

Ridge penalizes:

$$
\sum \beta_j^2
$$

The penalty depends on the scale of the features.

Imagine one feature is measured in:

- rupees

and another in:

- thousands of rupees.

Their coefficient sizes can be very different because of their units.

Therefore:

> **Scale the features before applying Ridge.**

## Rule 2 — Do not penalize the intercept

The intercept should not be shrunk.

Why?

The intercept controls the baseline level of predictions.

Shrinking the intercept toward zero can pull predictions toward zero instead of toward the mean.

So the regularization penalty is normally applied to the feature coefficients, not the intercept.

## Two important λ values

### λ = 0

When:

$$
\lambda=0
$$

there is no regularization.

So Ridge becomes:

> **Ordinary Least Squares (OLS).**

### λ → ∞

When λ becomes extremely large:

> Every coefficient moves toward zero.

The model becomes almost a **flat-line model**.

The session describes this as:

- very high bias
- very low variance

## Easy memory trick

- λ = 0 → **normal OLS**
- huge λ → **almost flat model**
