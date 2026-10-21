# Feature Scaling

## 1. What is scaling?

Suppose we have:

```text
Age = 20
Salary = 80000
```

Salary has much larger numerical values.

Some ML algorithms may give too much importance to salary simply because its numerical scale is larger.

Scaling puts features onto a comparable scale.

## 2. Standardization

Formula:

```text
z = (x - μ) / σ
```

Where:

- `x` = original value
- `μ` = mean
- `σ` = standard deviation

After standardization, the feature is approximately:

```text
mean = 0
standard deviation = 1
```

### Example

For:

```text
10, 20, 30
```

Mean:

```text
μ = 20
```

Population standard deviation:

```text
σ ≈ 8.16
```

For `x = 10`:

```text
z = (10 - 20) / 8.16
  ≈ -1.22
```

For `x = 20`:

```text
z = 0
```

For `x = 30`:

```text
z ≈ +1.22
```

So:

```text
10, 20, 30
↓
-1.22, 0, +1.22
```

## 3. Min-Max scaling

Formula:

```text
x' = (x - xmin) / (xmax - xmin)
```

For:

```text
10, 20, 30
```

Minimum = 10

Maximum = 30

So:

```text
10 → 0
20 → 0.5
30 → 1
```

The values are bounded in `[0, 1]`.

## 4. Standard vs Min-Max

### StandardScaler

- centers around 0
- standard deviation becomes 1
- less directly affected by extreme values than Min-Max
- still not completely immune to outliers

### MinMaxScaler

- puts values into a fixed range such as `[0, 1]`
- very sensitive to outliers

Example:

```text
10, 20, 30, 200
```

The 200 can make the smaller values get squeezed close to 0.

## 5. Robust scaling

Formula:

```text
x' = (x - median) / IQR
```

It uses median and IQR, making it useful when outliers are present.

## 6. Who needs scaling?

Usually important for:

- Linear Regression / Logistic Regression
- KNN
- SVM
- Gradient-descent-based models
- PCA

### Why?

Because these methods can depend on:
- distances
- penalties
- optimization geometry
- variance

## 7. Who usually does not need scaling?

Tree-based models:

- Decision Tree
- Random Forest
- XGBoost

Trees mainly care about the ordering/splitting of values.

A monotonic scaling normally preserves that ordering.

## 8. Golden rule

Never calculate scaling parameters using the test set.

Fit on training data:

```text
fit(train)
```

Then use the learned parameters to transform both:

```text
transform(train)
transform(test)
```

## 9. Exam memory

**Standard:** `(x - mean) / std`

**Min-Max:** `(x - min) / (max - min)`

**Robust:** `(x - median) / IQR`

**Outliers:** Robust scaling is often a good choice.

**Trees:** usually do not need scaling.
