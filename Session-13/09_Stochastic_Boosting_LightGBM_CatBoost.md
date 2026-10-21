# 9. Stochastic Gradient Boosting, LightGBM, and CatBoost

## Stochastic gradient boosting
Instead of fitting each tree using every training row, the algorithm uses a random fraction of rows. It may also sample columns (features).

This adds some bagging-like randomness to boosting and can reduce variance and help generalization.

- `subsample` controls row sampling in many boosting libraries.
- Column-sampling parameters control feature sampling.

## LightGBM
The lecture highlights that LightGBM grows trees **leaf-wise**. This can be fast on large datasets, though tree growth and tuning choices still matter.

## CatBoost
The lecture highlights CatBoost's handling of categorical features and its use of **ordered boosting**.

## Main takeaway
These tools share the broad boosting idea, but make different trade-offs in speed, handling of data types, and tree-building strategy.
