# Session 8 --- The Threshold Is a Business Decision

## What does logistic regression actually give us?

The model first gives a **probability**.

Example:

\[ P(y=1)=0.82 \]

The model has not necessarily made the final class decision yet.

We choose a **threshold**.

------------------------------------------------------------------------

## What is a threshold?

Suppose the threshold is:

\[ 0.5 \]

Then:

``` text
probability >= 0.5 → predict 1
probability < 0.5  → predict 0
```

For:

\[ p=0.82 \]

we predict class 1.

------------------------------------------------------------------------

## Important: 0.5 is not a law

A threshold of 0.5 is just a common default.

The appropriate threshold depends on the cost of mistakes.

The model produces a **ranking** of cases by probability.

The threshold converts that ranking into a **decision**.

------------------------------------------------------------------------

## Example: cancer screening

Suppose a model predicts whether a patient may have a disease.

A missed positive case can be very costly.

So we may want a **lower threshold**.

That makes the model more willing to classify someone as positive.

Goal:

> Reduce missed positive cases.

This tends to focus attention on **recall**.

------------------------------------------------------------------------

## Example: spam filtering

Suppose the model predicts whether an email is spam.

If we classify too many emails as spam, a real email may disappear into
the spam folder.

So we may want a **higher threshold**.

Goal:

> Be more careful before calling something positive.

This tends to focus attention on **precision**.

------------------------------------------------------------------------

## Key distinction

### Model

Produces:

\[ P(y=1\|x) \]

### Threshold

Converts that probability into:

``` text
0 or 1
```

So:

> **Threshold = decision rule, not the model itself.**

------------------------------------------------------------------------

## Memory trick

Think:

> **Probability tells you "how likely?"**
>
> **Threshold tells you "what should I do?"**
