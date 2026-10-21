# 10 — One Split Is Not Enough: Cross-Validation

## The problem with one train-validation split

Suppose we split the data once:

```text
Training data → model training
Validation data → model evaluation
```

The validation score depends on **which rows happened to be placed in the validation set**.

If we make another random split, we can get a different score.

So the validation score has its own **variance**.

## Why is this a problem?

Regularization is being used partly to control variance.

But if our measurement itself has high variance, our model evaluation is not very stable.

We want a more reliable measurement.

## K-Fold Cross-Validation

K-Fold Cross-Validation divides the data into **K folds**.

For example, with 5 folds:

```text
Fold 1 → validation
Folds 2-5 → training

Fold 2 → validation
Folds 1,3-5 → training

Fold 3 → validation
other folds → training

Fold 4 → validation
other folds → training

Fold 5 → validation
other folds → training
```

Every fold is used as validation exactly once.

## Final CV score

After getting K validation scores, calculate their average.

For example:

```text
0.84
0.86
0.85
0.83
0.87
```

The average gives the overall CV score.

The session also says to report the **standard deviation**.

So a result can be written like:

$$
\text{mean} \pm \text{standard deviation}
$$

## Main idea

> **K-Fold CV gives us several validation measurements instead of trusting one random split.**
