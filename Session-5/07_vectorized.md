# 7. Vectorized Gradient and Convexity

## Vectorized gradient

For linear regression, the gradient can be written compactly as:

`∇J(θ) = (1/m) Xᵀ(Xθ - y)`

This is the vectorized form.

Instead of calculating every parameter update with Python loops, we use
matrix operations.

## What do the symbols mean?

-   `X` = feature matrix
-   `Xᵀ` = transpose of X
-   `θ` = parameter vector
-   `y` = target vector
-   `m` = number of training examples

The expression:

`Xθ`

produces predictions.

Then:

`Xθ - y`

produces prediction errors.

Then:

`Xᵀ(Xθ - y)`

combines those errors with the features to produce the gradient.

Finally, divide by `m` to average across examples.

## Why vectorization matters

Matrix operations are efficient and can use optimized numerical
libraries and hardware.

This is one reason mini-batch methods work so well with modern CPUs and
GPUs.

------------------------------------------------------------------------

## What is convexity?

A convex cost surface is roughly like a bowl.

There is one global minimum.

For a convex problem:

-   you don't have many competing local minima
-   downhill movement can reach the global minimum if optimization is
    configured appropriately

This is good news for linear regression with the usual squared-error
cost.

## Why it matters

If the cost function is convex, we have a much easier optimization
landscape.

The file emphasizes:

**convex ⇒ one global minimum**

This makes Gradient Descent especially understandable for linear
regression.

## Important distinction

Not every ML model has a convex loss surface.

Neural networks, for example, generally involve non-convex optimization.

That is one reason optimization becomes more complicated in deep
learning.
