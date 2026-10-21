# 04 — Ridge on Two Points

## Example

We have two points:

- $(1,2)$
- $(2,4)$

We use a model with no intercept:

$$
\hat y=\beta x
$$

## Ordinary Linear Regression

For the two points:

$$
\sum x^2 = 1^2+2^2=5
$$

and

$$
\sum xy=(1)(2)+(2)(4)=10
$$

Without regularization, λ = 0:

$$
\beta=\frac{\sum xy}{\sum x^2}
=\frac{10}{5}
=2
$$

So the coefficient is **2**.

## Add Ridge regularization

For this simple example:

$$
\beta=
\frac{\sum xy}{\sum x^2+\lambda}
$$

Therefore:

$$
\beta=\frac{10}{5+\lambda}
$$

### Try different λ values

| λ | β |
|---:|---:|
| 0 | 2.0 |
| 1 | 1.67 |
| 5 | 1.0 |
| 15 | 0.5 |

## What do we learn?

As λ becomes larger:

> **The Ridge coefficient becomes smaller.**

For example:

- λ = 0 → β = 2
- λ = 1 → β ≈ 1.67
- λ = 5 → β = 1
- λ = 15 → β = 0.5

It moves toward zero.

The important point is:

> L2 gives **smooth shrinkage**. The coefficient approaches zero but does not reach it in the way Lasso can.
