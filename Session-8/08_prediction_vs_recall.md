# Session 8 --- Precision vs Recall: Pick Your Error

Precision and recall measure different kinds of mistakes.

------------------------------------------------------------------------

# Precision

Formula:

\[ Precision=`\frac{TP}{TP+FP}`{=tex} \]

Question:

> **When the model says positive, how often is it right?**

Precision is especially important when **false positives are costly**.

Example:

### Spam filtering

If the model marks a real email as spam, that is a false positive.

You may therefore care strongly about precision.

------------------------------------------------------------------------

# Recall

Formula:

\[ Recall=`\frac{TP}{TP+FN}`{=tex} \]

Question:

> **Of all the actual positive cases, how many did the model catch?**

Recall is especially important when **false negatives are costly**.

Examples:

-   disease screening
-   fraud detection
-   safety-related detection

Missing a real positive can be very costly.

------------------------------------------------------------------------

# Precision-recall trade-off

Changing the threshold can change precision and recall.

A common pattern is:

``` text
Higher threshold
    ↓
Fewer positive predictions
    ↓
Usually higher precision
    ↓
Usually lower recall
```

And:

``` text
Lower threshold
    ↓
More positive predictions
    ↓
Usually higher recall
    ↓
Usually lower precision
```

The exact behavior depends on the model and data, but this is the basic
trade-off.

------------------------------------------------------------------------

# Why is F1 a harmonic mean?

F1 is:

\[ F_1 = 2`\frac{PR}{P+R}`{=tex} \]

Suppose:

\[ P=1.0 \]

and:

\[ R=0.1 \]

The ordinary arithmetic mean would be:

\[ `\frac{1.0+0.1}{2}`{=tex}=0.55 \]

That can make the result look better than it really is.

F1 is approximately:

\[ 0.18 \]

So F1 strongly reflects the fact that one of the two metrics is very
low.

------------------------------------------------------------------------

# Easy memory trick

### Precision

> **"When I say positive, am I usually right?"**

### Recall

> **"Did I find most of the real positives?"**

And:

> **Precision cares about false positives.**
>
> **Recall cares about false negatives.**
