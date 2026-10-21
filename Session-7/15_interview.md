# 15 — Interview-Grade Questions

Use these questions to test yourself.

## Question 1 — Ridge or Lasso?

Ask yourself:

- When would Ridge be useful?
- When would Lasso be useful?
- What happens to coefficients?
- Which one can perform feature selection?

### Core recall

**Ridge:**

- L2
- smooth shrinking
- helps with multicollinearity

**Lasso:**

- L1
- can make coefficients zero
- feature selection

## Question 2 — Why does L1 zero coefficients?

Because the L1 constraint has a diamond-like shape with sharp corners.

The corners lie on axes.

When the error contour touches a corner, a coefficient can become exactly zero.

## Question 3 — How does λI help multicollinearity?

Ridge changes:

$$
X^TX
$$

to:

$$
X^TX+\lambda I
$$

The session explains that this lifts the eigenvalues and can make the matrix invertible when $X^TX$ is singular.

## Question 4 — Why must CV run inside a Pipeline?

Because preprocessing such as scaling can learn information from the data.

If scaling is done before CV on the complete dataset, validation information can leak into the process.

A Pipeline makes preprocessing happen separately inside each fold.

## Question 5 — Why report mean ± standard deviation?

Because the mean alone does not tell us how much the score changes between folds.

For example:

```text
0.85 ± 0.02
```

shows much less spread than:

```text
0.85 ± 0.15
```

## One formula to remember

Regularization follows the general pattern:

$$
\text{fit} + \lambda \times \text{complexity penalty}
$$

This is the same general idea of balancing fit and complexity discussed with Adjusted $R^2$.
