# 3. The Gradient Descent Update Rule

## The main formula

`θ := θ - α ∇J(θ)`

This is the most important formula in the session.

## Meaning of every part

### θ

`θ` represents the model parameters.

For a simple line:

`ŷ = θ₀ + θ₁x`

there are two parameters:

-   `θ₀`
-   `θ₁`

So Gradient Descent updates both.

### α --- learning rate

This controls how large a step we take.

### ∇J(θ) --- gradient

This tells us the direction and steepness of the cost.

### Why minus?

The gradient points uphill.

We want downhill.

Therefore:

`new parameter = old parameter - step`

## A simple numerical example

Suppose:

-   current `θ = 10`
-   learning rate `α = 0.1`
-   gradient = `4`

Then:

`θ_new = 10 - 0.1(4)`

`θ_new = 9.6`

So the parameter moves from `10` to `9.6`.

If the gradient were `-4`:

`θ_new = 10 - 0.1(-4)`

`θ_new = 10.4`

So the sign of the gradient automatically decides which direction the
parameter moves.

## General algorithm

``` text
initialize θ

repeat:
    calculate gradient
    θ = θ - α × gradient
```

This is why Gradient Descent is called an **iterative optimization
algorithm**.

It does not normally jump directly to the answer. It keeps improving the
parameters step by step.
