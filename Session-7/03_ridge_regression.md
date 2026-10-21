# 03 — Ridge Regression (L2 Regularization)

## What is Ridge?

Ridge Regression is Linear Regression with an extra penalty on the **squared coefficients**.

Its objective is:

$$
J(\beta)=\|y-X\beta\|^2+\lambda\sum_{j=1}^{p}\beta_j^2
$$

The important part is:

$$
\lambda\sum \beta_j^2
$$

This is called the **L2 penalty**.

## What does Ridge do?

Ridge makes coefficients smaller.

But according to this session's key rule:

> Ridge shrinks coefficients toward zero, but does not make them exactly zero.

So if a coefficient is 5, Ridge may make it 2, 1, 0.2, etc., depending on λ.

It normally does not suddenly become exactly 0.

## Ridge formula

The closed-form solution shown in the session is:

$$
\beta=(X^TX+\lambda I)^{-1}X^Ty
$$

The important new part is:

$$
X^TX+\lambda I
$$

## Ridge and multicollinearity

Ridge also helps with the multicollinearity problem.

The session explains that adding:

$$
\lambda I
$$

lifts the eigenvalues and can make the matrix invertible even when $X^TX$ is singular.

So remember:

> **Ridge + λI → helps repair multicollinearity.**

## Key memory trick

**Ridge = L2 = squares = smooth shrinking.**
