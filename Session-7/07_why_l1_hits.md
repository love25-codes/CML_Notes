
# 07 — Why L1 Hits the Axis

## The question

Why can Lasso make a coefficient exactly zero while Ridge usually does not?

The session explains this using **geometry**.

## Think about two coefficients

Suppose we have:

- β₁
- β₂

Regularization creates a constraint on how large these coefficients can be.

### L2 shape

L2 creates a **circle** in the two-coefficient case.

A circle has a smooth boundary.

When the error contours touch this boundary, the first touching point is generally not exactly on an axis.

So:

> Ridge generally keeps both coefficients non-zero.

### L1 shape

L1 creates a **diamond-like shape**.

A diamond has sharp **corners**.

Those corners lie directly on the axes.

If the error contour first touches the L1 region at a corner, one coefficient is exactly zero.

For example:

$$
\beta_1=0
$$

## Simple picture to remember

```text
L2 → circle → smooth edge → coefficients usually stay non-zero

L1 → diamond → sharp corner → coefficient can become exactly zero
```

## Main lesson

The zero coefficients produced by Lasso are not just a random trick.

They come naturally from the geometry of the L1 constraint.

## Memory trick

> **L1 has corners. Corners touch axes. Axes mean zero coefficients.**
