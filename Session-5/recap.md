# 12. Gradient Descent --- Quick Revision

## One-line definition

**Gradient Descent is an iterative optimization algorithm that
repeatedly changes model parameters in the direction that reduces the
cost function.**

## Main formula

`θ := θ - α∇J(θ)`

## Symbols

  Symbol    Meaning
  --------- ------------------
  `θ`       model parameters
  `α`       learning rate
  `J(θ)`    cost/loss
  `∇J(θ)`   gradient

## Mental picture

``` text
          high loss
             /\
            /  \
           /    \
          /  ↓   \
         /   ↓    \
        /    ↓     \
       /____ ↓ _____\
          minimum
```

## Learning rate

``` text
α too small  → slow
α good       → smooth + fast
α too large  → overshoot / diverge
```

## Variants

``` text
Batch       → all samples
SGD         → 1 sample
Mini-batch  → small group
```

## Scaling

``` text
Unscaled → narrow valley → zig-zag → slow
Scaled   → rounder bowl → straighter path → faster
```

## Gradient intuition

``` text
gradient = uphill direction
negative gradient = downhill direction
```

## Convexity

``` text
convex cost → bowl-shaped → one global minimum
```

## Practical checklist

Before trusting a Gradient Descent run, ask:

1.  Did I scale the features when appropriate?
2.  Is the learning rate reasonable?
3.  Is the loss decreasing?
4.  Is the loss curve stable?
5.  Has the algorithm converged?
6.  Am I using an appropriate batch strategy?

## Final memory trick

**LOOK → CALCULATE → STEP → REPEAT**

-   Look at current error.
-   Calculate gradient.
-   Take a downhill step.
-   Repeat until the loss stops improving.
