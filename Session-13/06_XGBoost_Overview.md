# 6. XGBoost: What It Adds

XGBoost is an optimized gradient-boosting method. It keeps the sequential boosting idea and adds techniques to control model complexity and train efficiently.

## Main features in the lecture

### 1. Regularized objective
It penalizes overly complex trees, helping control overfitting.

### 2. Second-order gradients (Hessian)
It uses information about both the gradient and the curvature of the loss to make better split and update decisions.

### 3. Sparsity-aware splits
It can handle missing values by learning a default direction for missing entries at a split.

### 4. Histogram / approximate splits
Instead of checking every possible split in an expensive way, it can use approximate or histogram-based methods to scale to larger datasets.

### 5. Parallel building and early stopping
Some tree-building work can be parallelized even though boosting rounds themselves depend on earlier rounds. Early stopping can halt training when validation performance stalls.

## When might you use it?
The lecture's suggested workflow is to start with Random Forest as a strong baseline, then try XGBoost if you want to improve performance on tabular data and are willing to tune it carefully.
