# Generalization — What We Actually Want

## 1. Core Idea

The goal of Machine Learning is **not** simply to perform well on the training data.

The real goal is:

> A model should perform well on **new, unseen data** drawn from the same underlying problem.

This ability is called **generalization**.

```text
Training Data
      ↓
    Model
      ↓
New / Unseen Data
      ↓
Good Predictions
```

---

# 2. Unknown Data Distribution 𝓓

In ML, we assume that data comes from some underlying probability distribution:

\[
\mathcal{D}
\]

The distribution is over:

\[
\mathcal{X} \times \mathcal{Y}
\]

where:

- `𝓧` = input/feature space
- `𝓨` = output/target space
- `𝓧 × 𝓨` = possible input-output pairs

Example for house-price prediction:

```text
𝓧 = house features
    - area
    - rooms
    - location
    - age

𝓨 = house price
```

The real-world distribution `𝓓` is generally unknown.

---

# 3. Finite Sample S

We cannot observe the entire distribution `𝓓`.

Instead, we only observe a finite sample:

\[
S = \{(x_1,y_1),(x_2,y_2),...,(x_m,y_m)\}
\]

where:

- `S` = observed dataset/sample
- `m` = number of examples
- `xᵢ` = features of example `i`
- `yᵢ` = actual target of example `i`

### Important

```text
Unknown real-world distribution
             ↓
             𝓓
             ↓
      Finite sample S
```

We only see `S`, but we care about performance on the entire distribution `𝓓`.

---

# 4. Model / Function f

A model can be represented as a function:

\[
f(x)
\]

It takes an input `x` and produces a prediction.

Example:

\[
f(x) = 2x + 5
\]

If:

\[
x=10
\]

then:

\[
f(10)=25
\]

---

# 5. Loss Function L

The loss function measures how wrong a prediction is.

General form:

\[
L(y,f(x))
\]

where:

- `y` = actual output
- `f(x)` = predicted output
- `L` = loss function

Example using absolute error:

\[
L(y,\hat y)=|y-\hat y|
\]

If:

```text
Actual = 30
Prediction = 25
```

then:

\[
L=|30-25|=5
\]

Different ML problems use different loss functions.

Examples:

- Mean Squared Error
- Mean Absolute Error
- Cross-Entropy / Log Loss
- 0-1 Loss

---

# 6. Training Error

The training error is:

\[
\overline{err}(f)
=
\frac{1}{m}
\sum_{i\in S}L(y_i,f(x_i))
\]

It is also commonly called **empirical risk**.

### Meaning

> Training error = Average loss of the model on the training dataset.

The process is:

```text
For every training example:
    Calculate prediction
    ↓
    Calculate loss
    ↓
Average all losses
    ↓
Training Error
```

---

# 7. Numerical Example of Training Error

Suppose:

| Actual | Prediction | Absolute Error |
|---:|---:|---:|
| 10 | 8 | 2 |
| 20 | 23 | 3 |
| 30 | 28 | 2 |
| 40 | 45 | 5 |

Total loss:

\[
2+3+2+5=12
\]

Number of examples:

\[
m=4
\]

Training error:

\[
\frac{12}{4}=3
\]

Therefore:

\[
\boxed{\text{Training Error}=3}
\]

---

# 8. True Error

The true error is:

\[
err(f)
=
\mathbb{E}_{(x,y)\sim\mathcal{D}}
[L(y,f(x))]
\]

It is also called:

- Expected risk
- Population risk
- Generalization error

depending on the context.

### Meaning

> True error = Expected loss of the model on data generated from the underlying distribution `𝓓`.

The symbol:

\[
\mathbb{E}
\]

means **expectation**, which can be understood as an average over the underlying distribution.

---

# 9. Training Error vs True Error

## Training Error

\[
\boxed{
\overline{err}(f)
=
\frac{1}{m}
\sum_{i\in S}L(y_i,f(x_i))
}
\]

Measures:

> Performance on the finite dataset we have.

## True Error

\[
\boxed{
err(f)
=
\mathbb{E}_{(x,y)\sim\mathcal{D}}
[L(y,f(x))]
}
\]

Measures:

> Expected performance on the entire underlying distribution.

### Main Difference

```text
Training Error → What we CAN measure directly
True Error     → What we ACTUALLY care about
```

---

# 10. Why Can't We Directly Calculate True Error?

The underlying distribution `𝓓` is unknown.

Therefore:

```text
Unknown:
𝓓
 ↓
True Error cannot usually be calculated directly
```

But we have:

```text
Known:
Finite sample S
 ↓
Training Error can be calculated
```

This creates a fundamental challenge in Machine Learning.

---

# 11. Generalization

Generalization means:

> The ability of a model to perform well on unseen data drawn from the same underlying distribution.

A model should not simply memorize its training data.

```text
Training Data
      ↓
    Model
      ↓
Unseen Data
      ↓
Good Performance
```

---

# 12. Training Error vs Generalization Error

Suppose:

```text
Training Error = 1%
True/Test Error = 20%
```

The model performs extremely well on training data but poorly on unseen data.

This indicates poor generalization and is often a sign of **overfitting**.

A better situation might be:

```text
Training Error = 18%
Test Error = 20%
```

The model generalizes much better.

---

# 13. Overfitting

Overfitting occurs when a model learns the training data too specifically and performs poorly on unseen data.

Typical pattern:

```text
Training Error → Very Low
Test Error     → High
```

or:

```text
Training Performance → Excellent
Test Performance     → Poor
```

### Intuition

The model has effectively memorized the training data instead of learning a pattern that generalizes.

---

# 14. Underfitting

Underfitting occurs when the model is too simple to capture the underlying pattern.

Typical pattern:

```text
Training Error → High
Test Error     → High
```

The model has not learned enough from the data.

---

# 15. Ideal Model

We want:

```text
Training Error → Low
Generalization/Test Error → Low
```

We do NOT simply want the smallest possible training error.

The actual goal is:

> **Low error with good generalization.**

---

# 16. Train/Test Split

We usually split the available dataset into separate parts.

Example:

```text
1000 examples
     ↓
800 → Training Set
200 → Test Set
```

The model learns using the training set.

Then we evaluate it on the test set.

```text
Training Set
     ↓
   Model
     ↓
Test Set
     ↓
Estimate Generalization
```

The test set provides an estimate of how the model may perform on unseen data.

---

# 17. Cross-Validation

Cross-validation is a technique used to obtain a more reliable estimate of model performance and help with model selection/hyperparameter tuning.

Example: **5-fold cross-validation**

```text
Dataset
   ↓
┌────┬────┬────┬────┬────┐
│ F1 │ F2 │ F3 │ F4 │ F5 │
└────┴────┴────┴────┴────┘
```

The model is trained on 4 folds and validated on the remaining fold.

This is repeated 5 times.

The validation results are then averaged.

---

# 18. Regularization

Regularization helps control model complexity and can reduce overfitting.

Instead of minimizing only the loss:

\[
Loss
\]

we can minimize:

\[
Loss + \lambda \times Complexity
\]

where:

- `λ` = regularization strength
- `Complexity` = penalty for complex model behavior

The idea is:

> Fit the data well, but avoid unnecessary complexity.

Examples:

- Ridge Regression
- Lasso Regression
- L1 Regularization
- L2 Regularization

---

# 19. Pruning

Pruning is especially associated with Decision Trees.

A tree that grows too deep may memorize the training data.

```text
Very Deep Tree
      ↓
    Pruning
      ↓
Simpler Tree
      ↓
Better Generalization
```

Pruning removes unnecessary branches or limits tree complexity.

---

# 20. The Generalization Gap

The difference between training performance/error and performance/error on unseen data is often referred to as the **generalization gap**.

Example:

```text
Training Accuracy = 99%
Test Accuracy     = 90%

Generalization Gap = 9 percentage points
```

A large gap can be a warning sign of overfitting.

---

# 21. Why These Techniques Exist

The slide mentions:

- Train/test splits
- Cross-validation
- Regularization
- Pruning

These techniques help us deal with the fundamental problem:

```text
We can measure:
Training Error
      ↓
But we care about:
True Error
```

Their purpose is to help us build models that generalize well and to estimate/control the gap between observed training performance and expected performance on unseen data.

---

# 22. Important Subtlety

The goal is NOT necessarily:

```text
Training Error = Test Error
```

A small difference is normal.

Example:

```text
Training Accuracy = 96%
Test Accuracy     = 93%
```

This can be perfectly reasonable.

But:

```text
Training Accuracy = 99.9%
Test Accuracy     = 65%
```

is a strong warning sign of overfitting.

The real goal is:

> **Good performance on unseen data.**

---

# 23. Complete Mental Model

```text
REAL WORLD
    ↓
Unknown Distribution 𝓓
    ↓
Finite Sample S
    ↓
Train Model
    ↓
Training Error
```

But what we actually care about:

```text
REAL WORLD
    ↓
Unknown Distribution 𝓓
    ↓
New / Unseen Data
    ↓
Model
    ↓
True / Generalization Error
```

The fundamental problem:

```text
Training Error → Directly measurable
True Error     → Not directly measurable
```

Therefore we use tools such as:

```text
Train/Test Split
Cross-Validation
Regularization
Pruning
```

to help us build models that generalize.

---

# 24. Key Takeaways

1. **Generalization** = performing well on unseen data.

2. Real-world data is assumed to come from an unknown distribution `𝓓`.

3. We only observe a finite sample `S`.

4. `X` represents the input/feature space.

5. `Y` represents the target/output space.

6. `f(x)` represents the model's prediction.

7. `L(y, f(x))` represents the loss of a prediction.

8. **Training error** is the average loss on the observed training sample.

9. **True error** is the expected loss over the underlying distribution.

10. We can directly measure training error, but generally cannot directly measure true error because `𝓓` is unknown.

11. **Overfitting** = low training error but poor performance on unseen data.

12. **Underfitting** = high training and test/generalization error because the model is too simple.

13. Train/test splits help estimate generalization performance.

14. Cross-validation helps with model evaluation and model selection.

15. Regularization controls model complexity and can reduce overfitting.

16. Pruning controls the complexity of decision trees.

17. The ultimate goal is **not minimum training error**.

18. The ultimate goal is:

    **Good performance on unseen data = Good Generalization**

### One-line summary

**We can measure how well a model fits the data we have, but we actually care about how well it performs on data we haven't seen.**