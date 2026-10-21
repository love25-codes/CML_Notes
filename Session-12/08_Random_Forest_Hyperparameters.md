# 8. Random Forest Hyperparameters

A **hyperparameter** is a setting chosen before or during model training that controls how the model is built.

| Parameter | Meaning | Guidance from the session |
|---|---|---|
| `n_estimators` | Number of trees in the forest | More trees are generally safe; 100–500 is a typical range |
| `max_features` | Number or fraction of features considered at each split | A key control for decorrelation; lower values usually increase decorrelation |
| `max_depth` | Maximum depth of each tree | The session says to usually leave it unlimited |
| `oob_score` | Whether to calculate an out-of-bag score | Useful for a validation-like estimate |
| `n_jobs` | Parallel-processing setting in scikit-learn | `n_jobs=-1` asks to use all available processors |

## Can more trees overfit a Random Forest?
The session's key point is that **adding more trees does not make a Random Forest overfit in the usual way**. More trees generally stabilise the ensemble, although they cost more computation.

This does not mean every possible model setting is perfect or that more trees are free: training and prediction can take longer and use more resources.

## Practical memory aid
- `n_estimators` → how many trees?
- `max_features` → how much feature randomness?
- `max_depth` → how deep can each tree grow?
- `oob_score` → estimate performance using left-out rows?
- `n_jobs` → how much parallel work?
