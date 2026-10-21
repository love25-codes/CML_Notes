# 4. Why the Conditional Mean Minimizes Squared Error

This is one of the most reusable results in machine learning.

For a fixed input `x`, let:

```text
ȳ = E[y | x]
```

Consider the error:

```text
y - f(x)
```

Rewrite it as:

```text
y - f(x) = (y - ȳ) + (ȳ - f(x))
```

Now square it and take the expectation.

The result becomes:

```text
E[(y - f(x))²]
=
E[(y - ȳ)²] + (ȳ - f(x))²
```

The cross-term disappears because:

```text
E[y - ȳ] = 0
```

## What does this mean?

The first part:

```text
E[(y - ȳ)²]
```

is the unavoidable variation/noise.

The second part:

```text
(ȳ - f(x))²
```

is the part we can control.

To make the total error smallest, we need:

```text
f(x) = ȳ
```

Therefore:

```text
f*(x) = E[y | x]
```

## Intuition
If you repeatedly observe outcomes for the same situation, the average outcome is the value that minimizes squared prediction error.

## Why it matters later
This idea is connected to:
- bias–variance
- regression
- tree leaf predictions
- KMeans centroids
