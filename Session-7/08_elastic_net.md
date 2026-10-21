# 08 — Elastic Net

## What is Elastic Net?

Elastic Net combines **L1 and L2 regularization**.

Its objective is:

$$
J(\beta)=\|y-X\beta\|^2
+\lambda_1\sum|\beta_j|
+\lambda_2\sum\beta_j^2
$$

So Elastic Net contains both:

- L1 penalty
- L2 penalty

## Why combine them?

Because Ridge and Lasso have different useful behaviors.

### Ridge

Ridge:

- shrinks coefficients
- does not normally make them exactly zero
- works well when many features are relevant
- is useful with multicollinearity

### Lasso

Lasso:

- shrinks coefficients
- can make coefficients exactly zero
- performs feature selection
- is useful when only a few features matter

### Elastic Net

Elastic Net:

- can shrink coefficients
- can make coefficients zero
- is useful when correlated features occur in groups
- is also useful when $p>n$

Here $p$ means number of features and $n$ means number of observations.

## The grouping effect

Suppose several features are strongly correlated.

The session says Lasso may arbitrarily keep one feature and set the others to zero.

Elastic Net tends to keep the correlated group together.

So remember:

> **Elastic Net = L1 + L2 = selection + grouping/shrinkage behavior.**
