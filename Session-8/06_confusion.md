# Session 8 --- Confusion Matrix & Metrics

## What is a confusion matrix?

A confusion matrix compares:

``` text
Actual answer
vs.
Model prediction
```

For binary classification there are four possible outcomes.

                Actual 1   Actual 0
  ------------- ---------- ----------
  Predicted 1   TP         FP
  Predicted 0   FN         TN

------------------------------------------------------------------------

## TP --- True Positive

The model predicted positive and the actual answer was positive.

Example:

``` text
Actual: spam
Prediction: spam
```

Correct positive.

------------------------------------------------------------------------

## TN --- True Negative

The model predicted negative and the actual answer was negative.

Example:

``` text
Actual: not spam
Prediction: not spam
```

Correct negative.

------------------------------------------------------------------------

## FP --- False Positive

The model predicted positive, but the actual answer was negative.

Example:

``` text
Actual: normal email
Prediction: spam
```

This is a **false alarm**.

------------------------------------------------------------------------

## FN --- False Negative

The model predicted negative, but the actual answer was positive.

Example:

``` text
Actual: spam
Prediction: not spam
```

This is a **miss**.

------------------------------------------------------------------------

# Precision

Precision answers:

> **Of everything I predicted as positive, how many were actually
> positive?**

Formula:

\[ `\text{Precision}`{=tex} = `\frac{TP}{TP+FP}`{=tex} \]

High precision means fewer false positives among predicted positives.

------------------------------------------------------------------------

# Recall

Recall answers:

> **Of all the actual positives, how many did I successfully find?**

Formula:

\[ `\text{Recall}`{=tex} = `\frac{TP}{TP+FN}`{=tex} \]

High recall means fewer false negatives.

------------------------------------------------------------------------

# F1 score

F1 combines precision and recall.

\[ F_1 = 2`\frac{Precision\cdot Recall}{Precision+Recall}`{=tex} \]

It is the **harmonic mean**, not the ordinary arithmetic mean.

------------------------------------------------------------------------

## Easy way to remember

### Precision

> **Predicted Positive → How many were correct?**

Look at:

\[ TP+FP \]

### Recall

> **Actual Positive → How many did I catch?**

Look at:

\[ TP+FN \]

Memory trick:

> **Precision = prediction side**
>
> **Recall = reality side**
