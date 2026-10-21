# 3. Why Do We Use Squared Error?

There are three important reasons.

## 1. Practical reason
Squared error is smooth and differentiable everywhere.

That makes calculus-based optimization easy.

Absolute error has a sharp corner at zero, which makes ordinary differentiation less convenient.

## 2. Statistical reason
Assume:

```text
y = Xβ + ε
```

where the noise is Gaussian:

```text
ε ~ N(0, σ²)
```

Under this assumption, minimizing squared error gives the **maximum likelihood estimate (MLE)**.

So MSE is connected directly to a probability model.

## 3. Decision-theoretic reason
If we want to minimize expected squared error, the best prediction is:

```text
f*(x) = E[y | x]
```

In words:

> The prediction that minimizes squared error is the conditional mean.

For comparison:

- squared error → conditional mean
- absolute error → conditional median

## Important lesson
Loss functions are not just arbitrary choices. They can be derived from mathematical, statistical, and decision-theoretic reasoning.
