# 6. Worked Example: Fit a Line by Hand

Data:

| Hours studied (x) | Score (y) |
|---:|---:|
| 1 | 1 |
| 2 | 3 |
| 3 | 3 |
| 4 | 5 |

The averages are:

```text
x̄ = 2.5
ȳ = 3
```

## Step 1: Calculate Sxy and Sxx

```text
Sxy = Σ(x - x̄)(y - ȳ) = 6
```

```text
Sxx = Σ(x - x̄)² = 5
```

For example, for the first row:

```text
(1 - 2.5)(1 - 3)
= (-1.5)(-2)
= 3
```

## Step 2: Find the slope

```text
β₁ = Sxy / Sxx
   = 6 / 5
   = 1.2
```

## Step 3: Find the intercept

```text
β₀ = ȳ - β₁x̄
   = 3 - 1.2(2.5)
   = 0
```

Therefore:

```text
ŷ = 1.2x
```

## Step 4: Make predictions

For x = 1, 2, 3, 4:

```text
ŷ = 1.2, 2.4, 3.6, 4.8
```

Residuals (`y - ŷ`):

```text
-0.2, 0.6, -0.6, 0.2
```

## Step 5: Calculate R²

```text
RSS = 0.8
TSS = 8
```

Therefore:

```text
R² = 1 - RSS/TSS
   = 1 - 0.8/8
   = 0.90
```

So the model explains **90% of the variation** in the scores.
