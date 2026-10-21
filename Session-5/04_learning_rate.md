# 4. Learning Rate

## What is the learning rate?

The learning rate, usually written as `α`, controls **how big each
Gradient Descent step is**.

In:

`θ := θ - α∇J(θ)`

`α` is the learning rate.

Think of it as the size of your footsteps while walking downhill.

## Learning rate too small

If `α` is very small:

-   steps are tiny
-   loss usually decreases slowly
-   training can take a very long time

So:

**too small = safe but slow**

## Learning rate about right

With a suitable learning rate:

-   loss decreases smoothly
-   parameters move toward the minimum
-   convergence is reasonably fast

So:

**good learning rate = smooth and fast descent**

## Learning rate too large

If `α` is too large:

-   the algorithm can jump over the minimum
-   it can oscillate
-   the loss can increase
-   it can eventually diverge
-   numerical values may overflow and become `NaN`

So:

**too large = unstable**

## How do we diagnose it?

Plot loss against iteration.

### Loss keeps rising

The learning rate may be too high.

### Loss is almost flat for hundreds of iterations

The learning rate may be too low.

### Loss decreases smoothly

The learning rate is probably reasonable.

## Learning-rate schedules

The file briefly mentions:

### Learning-rate decay

Start with a larger learning rate and reduce it over time.

### Adaptive methods

Methods such as:

-   RMSProp
-   Adam

adapt the effective step size for different parameters.

You will see these ideas more in deep learning.

## Interview point

A very common question is:

**What happens if the learning rate is too large?**

Answer:

It can overshoot the minimum, make the loss oscillate or increase, and
may cause divergence.
