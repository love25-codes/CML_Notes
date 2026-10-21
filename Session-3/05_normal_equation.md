# 5. Normal Equation: Closed-Form Solution

For linear regression with squared error, we can find the best coefficients directly.

The key geometric fact is:

> At the best solution, the residual is perpendicular to every column of `X`.

Write the residual as:

```text
e = y - Xβ
```

Orthogonality gives:

```text
Xᵀ(y - Xβ) = 0
```

Expand:

```text
Xᵀy - XᵀXβ = 0
```

Move terms:

```text
XᵀXβ = Xᵀy
```

If `XᵀX` is invertible:

```text
β = (XᵀX)⁻¹Xᵀy
```

This is the **normal equation**.

## Why this is useful
It gives the optimal linear-regression coefficients without repeatedly taking small optimization steps.

## Geometric meaning
The prediction:

```text
ŷ = Xβ
```

is the orthogonal projection of `y` onto the column space of `X`.

## Important limitation
`XᵀX` is a `p × p` matrix. If features are perfectly collinear, it may not have an inverse.
