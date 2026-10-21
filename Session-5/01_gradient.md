# 1. Gradient Descent --- Big Picture

## What is Gradient Descent?

Gradient Descent is a method used to find the **best values of model
parameters** by repeatedly moving toward a lower value of the cost/loss
function.

Think of a ball on a hill:

-   The **height** = loss/cost.
-   The **bottom of the hill** = minimum loss.
-   The ball = current model parameters.
-   Gradient Descent tells the ball which direction is downhill.

The file describes Gradient Descent as the optimisation engine behind
models such as linear regression, logistic regression, boosting, and
neural networks.

## Why do we need it?

For some problems, we can calculate the best parameters directly using a
closed-form formula such as the normal equation.

But a closed-form solution can become expensive when there are many
features, and it is not available for every model. Gradient Descent
gives us a general iterative method that works with differentiable cost
functions.

## Basic process

1.  Start with some parameter values.
2.  Calculate how bad the model currently is.
3.  Calculate the gradient of the cost.
4.  Move the parameters in the downhill direction.
5.  Repeat.
6.  Stop when the cost has become sufficiently small or the parameters
    have stopped changing.

## Main things to learn

The file focuses on:

-   the gradient
-   the learning rate
-   the update rule
-   batch, stochastic and mini-batch Gradient Descent
-   feature scaling
-   vectorized implementation
-   convexity
-   convergence and loss curves
-   a hand-worked example

## One formula to remember

`θ := θ - α ∇J(θ)`

Where:

-   `θ` = model parameters
-   `α` = learning rate
-   `J(θ)` = cost function
-   `∇J(θ)` = gradient of the cost

The minus sign is important because the gradient points **uphill**,
while we want to move **downhill**.
