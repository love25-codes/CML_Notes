# 7. Random Forest: Bagging Plus Feature Randomness

## What is a Random Forest?
A **Random Forest (RF)** combines two sources of randomness:

1. **Bootstrap sampling of rows** — the bagging part.
2. **Randomly choosing a subset of features at each split** — the extra step that helps decorrelate trees.

## Why randomise features?
Suppose one feature is extremely strong. With ordinary bagging, many trees may choose that same feature for their first split. The trees can then look very similar and make similar errors.

If each split can consider only a random subset of features, different trees may choose different splits. Their correlation can fall, reducing the correlation floor in the variance formula.

## The trade-off
Restricting the available features may prevent a tree from choosing its best possible split at a particular node. This can slightly increase each tree's bias, but the reduction in correlation can lower the ensemble's variance.

## One-line definition
**Random Forest = bagging + deliberate decorrelation through random feature subsets.**

## Defaults mentioned in the session
- Classification: `max_features='sqrt'`
- Regression: `max_features=1.0`

These are the defaults stated in the uploaded session notes; defaults can depend on the library and version being used.
