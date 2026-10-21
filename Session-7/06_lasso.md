# 06 — Lasso (L1 Regularization)

## What is Lasso?

Lasso is another regularization method.

Its objective is:

$$
J(\beta)=\|y-X\beta\|^2+
\lambda\sum_{j=1}^{p}|\beta_j|
$$

The important part is:

$$
\lambda\sum|\beta_j|
$$

This is called the **L1 penalty**.

## What makes Lasso special?

Lasso can make coefficients **exactly zero**.

For example:

```text
Feature A → coefficient = 2.3
Feature B → coefficient = 0
Feature C → coefficient = -1.1
```

Feature B has effectively been removed from the model.

Therefore:

> **Lasso performs automatic feature selection.**

## Why is that useful?

If some features are not useful, Lasso can push their coefficients to exactly zero.

So the final model can use fewer features.

## Ridge vs Lasso

### Ridge

- Uses L2.
- Shrinks coefficients.
- Usually keeps coefficients non-zero.

### Lasso

- Uses L1.
- Shrinks coefficients.
- Can make coefficients exactly zero.
- Therefore can perform feature selection.

## How is Lasso solved?

The session notes that Lasso has no simple closed-form solution because the absolute-value function has no derivative at zero.

The method mentioned for solving it is:

> **Coordinate descent**

## Easy memory trick

**Lasso = L1 = absolute value = zeros = feature selection.**
