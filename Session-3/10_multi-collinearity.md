# 10. Duplicate Features, Collinearity, and Singularity

Suppose the design matrix contains two identical feature columns:

```text
x₁ = x₂
```

The features contain exactly the same information.

This creates **perfect multicollinearity**.

## What happens?

The matrix:

```text
XᵀX
```

becomes singular.

A singular matrix does not have an ordinary inverse.

Therefore this formula fails:

```text
β = (XᵀX)⁻¹Xᵀy
```

## Why is there no unique solution?

If two features are duplicates, the model can split their effect in many different ways.

For example, if the combined effect needs to be 10:

```text
β₁ = 5, β₂ = 5
```

or:

```text
β₁ = 7, β₂ = 3
```

may produce the same predictions.

So the predictions can be well-defined while the individual coefficients are not uniquely determined.

## Connection to the next topic
This is the first warning about **multicollinearity**.

Later, multicollinearity becomes important when interpreting coefficients and understanding unstable estimates.
