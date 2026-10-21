# Session 8 --- ROC & AUC

## What is ROC?

ROC stands for **Receiver Operating Characteristic**.

The ROC curve plots:

-   **TPR** on the y-axis
-   **FPR** on the x-axis

------------------------------------------------------------------------

## TPR

True Positive Rate is:

\[ TPR=`\frac{TP}{TP+FN}`{=tex} \]

This is the same quantity as:

\[ Recall \]

So:

> **TPR = Recall**

------------------------------------------------------------------------

## FPR

False Positive Rate is:

\[ FPR=`\frac{FP}{FP+TN}`{=tex} \]

It measures the fraction of actual negatives that were incorrectly
classified as positive.

------------------------------------------------------------------------

# What is AUC?

AUC means **Area Under the ROC Curve**.

The session gives a useful interpretation:

> AUC is the probability that a randomly selected positive example is
> ranked above a randomly selected negative example.

This is about **ranking quality**.

------------------------------------------------------------------------

## Important AUC values

### AUC = 0.5

This is approximately random ranking.

Think:

> coin flip

### AUC = 1.0

This represents perfect ranking.

Every positive is ranked above every negative.

------------------------------------------------------------------------

# Why is AUC called threshold-independent?

A particular threshold gives one specific decision rule.

AUC considers the model's ranking across different thresholds.

So it does not depend on just one selected threshold.

------------------------------------------------------------------------

# Important distinction

Accuracy asks:

> How many final predictions were correct?

AUC asks more like:

> Does the model generally rank positives above negatives?

These are different questions.

------------------------------------------------------------------------

# Memory trick

Remember:

``` text
ROC → TPR vs FPR
AUC → area under ROC
AUC → ranking quality
```

And:

\[ TPR=Recall \]
