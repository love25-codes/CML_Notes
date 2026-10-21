# 2. Cost Function and Gradient

## Cost function

A model needs a way to measure how wrong its predictions are.

That measurement is called the **cost function** or **loss function**.

For the simple linear regression case in the file:

`J(θ) = 1/(2m) Σ(ŷᵢ - yᵢ)²`

and

`ŷᵢ = θ₀ + θ₁xᵢ`

Here:

-   `m` = number of training examples
-   `yᵢ` = actual answer
-   `ŷᵢ` = predicted answer
-   `θ₀` = intercept
-   `θ₁` = slope

## Why square the error?

The error is:

`prediction - actual`

Squaring it:

-   makes negative and positive errors both positive
-   makes large errors matter more
-   gives us a smooth function that is easy to differentiate

The `1/(2m)` factor is mainly a convenient scaling factor. The `2`
cancels with the `2` produced by differentiating a square.

## What is a gradient?

A gradient tells us **which direction makes the cost increase fastest**.

Imagine standing on a mountain:

-   gradient points toward steepest uphill
-   negative gradient points toward steepest downhill

Therefore Gradient Descent uses the **negative gradient**.

## In simple words

Gradient = "Which way should I move to reduce the error?"

The file also summarizes the linear-regression gradient idea as:

**gradient = error × feature**

For one parameter, this gives intuition for why a large prediction error
or a large feature can create a larger parameter update.

## Why does the step get smaller near the minimum?

Near the minimum, the curve becomes flatter.

So:

-   far from the minimum → slope is large → bigger movement
-   near the minimum → slope is small → smaller movement

The algorithm naturally slows down as it approaches the bottom.
