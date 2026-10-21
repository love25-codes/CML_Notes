# Session 8 --- Handling Class Imbalance

The session presents several approaches for handling class imbalance.

The important idea is not to blindly apply every technique.

------------------------------------------------------------------------

# 1. class_weight='balanced'

This is a relatively cheap first approach.

The model gives more importance to the minority class.

In scikit-learn, many classifiers support:

``` python
class_weight="balanced"
```

The goal is to stop the majority class from dominating the learning
process.

------------------------------------------------------------------------

# 2. Threshold tuning

Instead of automatically using:

\[ threshold=0.5 \]

you can choose a threshold based on the **business cost of errors**.

Example:

If missing a fraud case is very costly, you may want a threshold that
makes the model more willing to flag cases.

The key idea:

> The threshold is a decision setting.

------------------------------------------------------------------------

# 3. Resampling / SMOTE

Another option is to change the training data distribution.

SMOTE stands for **Synthetic Minority Over-sampling Technique**.

It creates synthetic minority-class examples.

The session describes resampling and SMOTE as powerful techniques, but
they must be used correctly.

------------------------------------------------------------------------

# The big warning: leakage

Suppose you perform SMOTE before cross-validation.

If information from a validation fold is used to create synthetic
training examples, the validation data has indirectly influenced
training.

That is **data leakage**.

The validation fold is no longer a clean test of the model.

------------------------------------------------------------------------

# Correct idea

For every CV fold:

``` text
Training fold
    ↓
fit resampling / SMOTE
    ↓
train model
    ↓
validation fold stays untouched
    ↓
evaluate
```

The important rule is:

> **Anything learned from the data must be fitted using training data
> only.**

This is the same general idea as avoiding preprocessing leakage.

------------------------------------------------------------------------

# Order to remember

The session presents:

1.  `class_weight='balanced'`
2.  Threshold tuning based on business cost
3.  Resampling / SMOTE inside the CV fold

The goal is to handle imbalance without contaminating validation data.

------------------------------------------------------------------------

## Memory trick

> **SMOTE inside the fold, not before the fold.**

And the general rule:

> **Train data teaches; validation data evaluates.**
