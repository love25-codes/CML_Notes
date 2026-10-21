# 2. Matrix Form and Cost Function

## Matrix form
Instead of writing every prediction separately, we can write all predictions together:

```text
ŷ = Xβ
```

Typical dimensions:

```text
ŷ : n × 1
X : n × p
β : p × 1
```

`X` is called the **design matrix**. A column of ones is usually included so that the model can learn the intercept.

## Residual
For observation `i`:

```text
eᵢ = yᵢ - ŷᵢ
```

A residual is simply:

> actual value − predicted value

## Mean Squared Error (MSE)

```text
MSE = (1/n) Σ(yᵢ - ŷᵢ)²
```

Training means choosing `β` so that this cost becomes as small as possible.

## Simple intuition
Suppose actual scores are:

```text
[50, 60, 70]
```

and predictions are:

```text
[48, 63, 68]
```

Errors are:

```text
[2, -3, 2]
```

Squaring gives:

```text
[4, 9, 4]
```

The squared errors are then averaged.

## Remember
Training = choose model parameters that minimize the cost function.
