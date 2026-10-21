# 06 — Polynomial Regression

## 1. What is polynomial regression?

Polynomial regression extends a simple linear model by adding powers of the input.

For one feature:

\[
y=\beta_0+\beta_1x+\beta_2x^2+\cdots
\]

For example, degree 3:

\[
y=\beta_0+\beta_1x+\beta_2x^2+\beta_3x^3
\]

## 2. Why use polynomial regression?

A straight line can only represent a limited relationship.

Adding polynomial terms lets the model represent curves.

For example:

```text
Degree 1 → straight line
Degree 2 → can make a curve
Degree 3 → more flexible curve
Degree 15 → very flexible
```

So polynomial degree becomes a **complexity dial**.

## 3. What happens when degree increases?

Increasing degree makes the model more expressive.

Generally:

```text
Degree ↑
    ↓
Model complexity ↑
    ↓
Bias tends to ↓
Variance tends to ↑
```

If the degree becomes excessively high, the model can start following noise.

That is overfitting.

## 4. Why is polynomial regression still called a linear model?

This is a very important exam question.

Consider:

\[
y=\beta_0+\beta_1x+\beta_2x^2
\]

It is not linear in `x` because `x²` appears.

But it **is linear in the parameters**:

```text
β0
β1
β2
```

The parameters appear only as coefficients multiplied by known features.

The session says:

> Linear in the parameters, not linear in x.

Therefore polynomial regression can still be treated as linear regression after transforming the features.

## 5. Design matrix idea

Suppose the original feature is:

```text
x
```

For degree 2, transform it into:

```text
[1, x, x²]
```

For degree 3:

```text
[1, x, x², x³]
```

The regression algorithm then works with these transformed columns.

The session summarizes this as:

> We only changed the design matrix.

## 6. Important exam question

### Q: Why is polynomial regression still a linear model?

Answer:

> Because it is linear in the parameters `β`, even though it is nonlinear in the input `x`.

## 7. Relationship with bias and variance

Low-degree polynomial:

```text
Too simple
→ high bias
→ possible underfitting
```

Very high-degree polynomial:

```text
Very flexible
→ high variance
→ possible overfitting
```

A suitable degree attempts to balance the two.
