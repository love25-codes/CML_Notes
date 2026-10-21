# 8. Practical XGBoost Tuning

The lecture suggests tuning parameters in this order:

| Order | Parameter | What it controls |
|---:|---|---|
| 1 | `learning_rate` | Size of each boosting update; start low, around `0.05` |
| 2 | `max_depth` | Tree complexity / capacity; a strong control on overfitting |
| 3 | `min_child_weight` | Restricts splits that have too little weight in a child; can reduce overfitting |
| 4 | `subsample` | Fraction of training rows sampled for each boosting round |
| 4 | `colsample_*` | Fraction of features sampled |
| 5 | `reg_*` | Regularization, including L1/L2 penalties |

## Suggested approach
1. Establish a baseline and choose an evaluation metric.
2. Use a relatively small learning rate.
3. Tune tree depth and `min_child_weight`.
4. Try row and feature subsampling.
5. Adjust regularization.
6. Use validation-based early stopping.

## Early stopping is especially important
Monitor a validation metric and stop if it does not improve for a set number of rounds. Keep the iteration with the best validation result.

Avoid judging a model only by training accuracy. The real question is how well it performs on data it did not train on.
