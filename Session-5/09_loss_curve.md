# 9. Loss Curve and Convergence

## What is a loss curve?

A loss curve plots:

-   x-axis = iteration
-   y-axis = loss/cost `J`

It shows whether training is improving.

## Healthy curve

A healthy Gradient Descent run generally shows the loss decreasing
toward a stable value.

It may decrease quickly at first and then flatten as it approaches the
minimum.

## Learning rate too small

The curve decreases very slowly.

This means:

-   training is stable
-   but convergence takes too long

## Learning rate too large

The curve may:

-   oscillate
-   rise
-   explode
-   eventually produce `NaN`

This indicates that the updates are too aggressive.

## Why does the curve flatten?

Near the minimum, the gradient becomes smaller.

Because the update contains the gradient:

`step = α × gradient`

the step naturally becomes smaller.

So the algorithm slows down as it approaches the minimum.

## What is convergence?

Convergence means the algorithm has reached a point where additional
updates produce very little improvement.

Possible stopping ideas include:

-   loss changes very little
-   parameters change very little
-   gradient becomes very small
-   a maximum number of iterations is reached

## Practical rule

The file gives a very useful debugging rule:

**If loss rises → suspect learning rate is too high.**

**If loss stays flat for a very long time → suspect learning rate is too
low.**

Plotting the loss curve is therefore a simple but powerful diagnostic
tool.
