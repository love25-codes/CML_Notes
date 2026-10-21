# Session 8 --- Where We Are Going Today

## What is this session about?

This session is about **Logistic Regression**, how we measure a
classification model, and what to do when one class is much more common
than the other.

The session focuses on four big goals:

1.  Build logistic regression from the **sigmoid**.
2.  Understand **log-loss** and why it is used instead of ordinary MSE.
3.  Read a **confusion matrix** and calculate classification metrics.
4.  Understand **class imbalance** so that a high accuracy score does
    not fool you.

------------------------------------------------------------------------

## Why not ordinary linear regression for 0/1 targets?

Suppose the target is:

-   `0` = not spam
-   `1` = spam

If we use ordinary linear regression, predictions can be outside the
range 0 to 1.

For example, it might predict:

-   `-0.3`
-   `0.7`
-   `1.4`

But a probability should be between **0 and 1**.

So we need a function that takes any number from:

\[ (-`\infty`{=tex},`\infty`{=tex}) \]

and converts it into:

\[ (0,1) \]

That function is the **sigmoid**.

------------------------------------------------------------------------

## Big picture

The basic flow is:

``` text
Features
   ↓
Linear equation
z = β₀ + β₁x₁ + β₂x₂ + ...
   ↓
Sigmoid
   ↓
Probability
   ↓
Threshold
   ↓
Class 0 or Class 1
```

For example:

``` text
z = 2
↓
sigmoid(2) ≈ 0.88
↓
probability of class 1 = 88%
↓
if threshold = 0.5
↓
predict class 1
```

------------------------------------------------------------------------

## What to remember

**Logistic Regression = linear equation + sigmoid + probability +
decision threshold.**

Memory trick:

> **Linear score → Sigmoid → Probability → Threshold → Class**
