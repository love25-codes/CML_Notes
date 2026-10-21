# 12. Interview Questions and Final Recap

## Question 1
### Give three reasons squared error is commonly used.

Answer:
1. It is differentiable and convenient for optimization.
2. Under Gaussian noise, least squares is the maximum likelihood estimate.
3. It is minimized by the conditional mean.

## Question 2
### Derive the normal equation.

Start with orthogonality:

```text
Xᵀ(y - Xβ) = 0
```

Then:

```text
XᵀXβ = Xᵀy
```

Therefore:

```text
β = (XᵀX)⁻¹Xᵀy
```

when the inverse exists.

## Question 3
### What does it mean that ŷ is a projection?

`ŷ` is the closest point to `y` inside the column space of `X`.

The residual is perpendicular to that space.

## Question 4
### Why does R² never decrease when adding a feature?

The additional feature gives the optimization more freedom. At worst, the model can effectively ignore it, so the training residual sum of squares cannot increase.

## Question 5
### Why can't we always use the normal equation?

Three reasons:
1. Matrix inversion can be expensive for large numbers of features.
2. `XᵀX` may be singular because of collinearity.
3. Many models do not have a closed-form solution.

## Two facts to remember

### Fact 1
```text
MSE ↔ MLE under Gaussian noise
```

### Fact 2
```text
ŷ = Xβ
```

is the orthogonal projection of `y` onto the feature space.

## Session in one flow

```text
Data
  ↓
Linear model
  ↓
Predictions ŷ = Xβ
  ↓
Residuals y - ŷ
  ↓
Minimize squared error
  ↓
Orthogonality
  ↓
Normal equation
  ↓
Projection interpretation
  ↓
Evaluate with R² / adjusted R²
  ↓
Recognize limitations
  ↓
Gradient descent
```

## The main lesson

Linear regression is not just a formula for drawing a line.

It connects:
- modeling
- optimization
- geometry
- probability
- statistics
- model evaluation
- computational complexity
