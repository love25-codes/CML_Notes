# 02 — Bias–Variance Trade-off

## 1. What are bias and variance?

Bias and variance describe two different ways a model can make mistakes.

### Bias

Bias is related to how far the model's average prediction is from the true relationship.

High bias usually means the model is too simple.

```text
High bias → underfitting
```

### Variance

Variance describes how much the model's prediction changes when we train it on a different sample of data.

High variance means the model is very sensitive to the particular training sample.

```text
High variance → overfitting
```

## 2. Why is there a trade-off?

Imagine increasing model complexity.

At first, increasing complexity is useful because a very simple model may not capture the real pattern.

As complexity increases:

- bias tends to decrease
- variance tends to increase

The session describes the classic U-shaped total-error picture.

```text
Error
 ^
 | \          /
 |  \        /
 |   \______/
 +----------------> Model complexity
```

The lowest total error is generally somewhere in the middle.

## 3. Three regimes

### Low complexity

The model is too simple.

```text
Bias: high
Variance: low
```

This is underfitting.

### Middle complexity

The model is sufficiently expressive without becoming excessively sensitive.

```text
Bias: lower
Variance: manageable
```

This is the useful middle region.

### Very high complexity

The model can chase the training data and its noise.

```text
Bias: low
Variance: high
```

This is overfitting.

## 4. Total error

The central relationship from the session is:

```text
Total error = bias² + variance + irreducible noise
```

The three components are:

1. Bias²
2. Variance
3. Irreducible noise

## 5. Important distinction

Bias and variance are **reducible**.

Irreducible noise is not something the model can simply remove.

So machine learning is largely about finding a useful balance between bias and variance.

## 6. Easy analogy

Imagine adjusting the focus of a camera:

- Too simple / not enough detail → blurry picture → high bias.
- Too sensitive to every tiny detail → captures noise → high variance.
- Good balance → useful picture.

## 7. Exam memory trick

```text
Simple model → Bias ↑, Variance ↓
Complex model → Bias ↓, Variance ↑
```

Remember:

> **Bias = model too rigid.**
>
> **Variance = model too sensitive.**
