# 1. Linear Regression Model

## Big idea
Linear regression tries to predict a number (such as exam score or house price) using one or more input features.

### One feature
```text
ŷ = β₀ + β₁x
```

- `ŷ` = predicted value
- `x` = input feature
- `β₀` = intercept
- `β₁` = coefficient/slope

Example:
```text
score = 40 + 5 × hours_studied
```
If a student studies 3 hours, predicted score = 55.

### Multiple features
```text
ŷ = β₀ + β₁x₁ + β₂x₂ + ... + βₚxₚ
```

For a coefficient, the important interpretation is:

> Holding all other features constant, increasing `xⱼ` by one unit changes the prediction by `βⱼ`.

### Geometry
- 1 feature → a line
- 2 features → a plane
- many features → a hyperplane

## Remember
Linear regression learns coefficients that make predictions as close as possible to the observed values.
