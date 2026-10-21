# 14 — Paths, Stability, and a Leak

This section describes a practical notebook demonstration.

## 1. Ridge vs Lasso coefficient paths

Plot coefficients against:

$$
\log(\lambda)
$$

You should see:

- Ridge coefficients shrink smoothly.
- Lasso coefficients can become exactly zero.

## 2. Count Lasso survivors

Because Lasso can set coefficients to zero, we can count how many coefficients remain non-zero.

This gives a simple way to see how much feature selection Lasso is performing.

## 3. Single split vs 5-fold CV

A single train/validation split can give a score that changes depending on the split.

Five-fold CV gives several measurements and lets us look at:

- mean score
- score stability / standard deviation

## 4. GridSearchCV over alpha

The notebook demonstrates searching over the regularization parameter, commonly called **alpha** in scikit-learn-style APIs.

The search is placed inside a Pipeline.

## 5. Demonstrating leakage

The notebook compares:

```text
CV after pre-scaling
```

with:

```text
CV using a Pipeline
```

The scores can differ.

The important lesson is not simply that the numbers differ.

The important lesson is:

> If preprocessing was fitted using information from validation folds, the evaluation contains leakage.

## Main memory point

A correct workflow keeps learned preprocessing inside the CV loop.
