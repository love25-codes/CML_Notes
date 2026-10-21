# Session 8 --- Class Imbalance & the Accuracy Trap

## What is class imbalance?

Class imbalance means one class appears much more often than the other.

Example:

``` text
99% legitimate transactions
1% fraud transactions
```

Fraud is the minority class.

------------------------------------------------------------------------

# The 99% accuracy trap

Imagine a fraud dataset with:

``` text
99 legitimate
1 fraud
```

A terrible model could simply predict:

``` text
Everything = legitimate
```

Then:

-   99 predictions are correct
-   1 fraud is missed

Accuracy:

\[ `\frac{99}{100}`{=tex}=99% \]

That sounds impressive.

But the model catches:

\[ 0 \]

fraud cases.

So the accuracy score hides the real problem.

------------------------------------------------------------------------

# Baseline is important

Whenever you see a high accuracy score on an imbalanced dataset, ask:

> What would happen if I always predicted the majority class?

That gives you a simple baseline.

If your model barely improves on that baseline, accuracy alone is not
telling you much.

------------------------------------------------------------------------

# Why ROC-AUC can also be misleading

Under extreme imbalance, the denominator of FPR contains many true
negatives:

\[ FPR=`\frac{FP}{FP+TN}`{=tex} \]

When `TN` is huge, even many false positives may produce a relatively
small FPR.

So ROC-AUC can sometimes look good even when performance on the rare
positive class is not what you need.

------------------------------------------------------------------------

# PR-AUC

PR-AUC focuses on:

-   Precision
-   Recall

When positive cases are rare, the session recommends considering
**PR-AUC** because it directly focuses on the positive-class detection
problem.

------------------------------------------------------------------------

# What should you remember?

For imbalanced classification:

``` text
Do not automatically trust accuracy.
Check the class distribution.
Compare against a majority-class baseline.
Look at precision and recall.
Consider PR-AUC when positives are rare.
```

------------------------------------------------------------------------

## Memory trick

> **Imbalance can make accuracy lie.**

Always ask:

> **"How many positive cases are actually there?"**
