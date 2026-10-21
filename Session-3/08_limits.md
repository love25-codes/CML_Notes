# 8. Why We Do Not Always Use the Closed Form

The normal equation is elegant:

```text
β = (XᵀX)⁻¹Xᵀy
```

But it is not always the best solution.

## 1. Matrix inversion can be expensive
Computing the inverse of `XᵀX` has roughly:

```text
O(p³)
```

complexity.

When the number of features `p` becomes very large, this can become expensive.

## 2. Singular matrix
If features are perfectly collinear, `XᵀX` may be singular.

Example:

```text
x₂ = 2x₁
```

The two columns contain redundant information.

Then the inverse may not exist.

## 3. Other models have no closed form
Linear regression with squared error has a convenient formula.

But models such as logistic regression generally do not have a simple closed-form solution.

## So what do we use?
We need a general optimization method that can work with differentiable cost functions.

That method is **gradient descent**.

The basic idea is:

1. Start with some parameter values.
2. Calculate the gradient.
3. Move parameters in the direction that decreases the cost.
4. Repeat.

This is the topic of the next session.
