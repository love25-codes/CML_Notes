# 6. Why Feature Scaling Speeds Up Gradient Descent

## The problem

Suppose a dataset has two features:

-   age: 0--100
-   salary: 20,000--2,000,000

These features live on very different scales.

This can make the cost surface stretched and narrow.

## What does the loss surface look like?

Imagine contour lines around the minimum.

### Without scaling

The contours can look like a long, thin valley.

Gradient Descent can then:

1.  move too far in one direction
2.  correct itself
3.  move too far in another direction
4.  repeat

The result is a zig-zag path toward the minimum.

It may converge slowly.

### With scaling

The contours become more rounded.

The gradient points more directly toward the minimum.

So Gradient Descent can take a much straighter path.

## Simple intuition

Imagine trying to walk to the bottom of a very narrow valley.

Without scaling:

-   one direction is extremely wide
-   another direction is extremely narrow
-   finding the bottom takes many corrections

With scaling:

-   the valley becomes more balanced
-   movement toward the minimum is easier

## Important point

Feature scaling does **not** magically change the underlying prediction
problem.

It changes the geometry of the optimization problem so that Gradient
Descent can navigate it more efficiently.

## Connection to preprocessing

This is the reason scaling methods such as StandardScaler are important
when using Gradient Descent-based models.

The file explicitly connects this explanation to the earlier scaling
concept: now we understand **why** scaling helps rather than simply
memorizing that we should scale features.
