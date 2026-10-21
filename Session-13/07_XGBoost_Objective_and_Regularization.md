# 7. XGBoost Objective and Regularization

XGBoost balances two goals: make accurate predictions and avoid unnecessarily complex trees.

## Objective

\[
\mathcal{L}=\sum_i L(y_i,\hat{y}_i)+\sum_m\Omega(f_m)
\]

- The first term measures prediction error.
- The second term penalizes model complexity.
- \(f_m\) is a tree in the ensemble.

The lecture gives this tree-complexity penalty:

\[
\Omega(f)=\gamma T+\frac{1}{2}\lambda\lVert w\rVert^2
\]

- \(T\): number of leaves in the tree.
- \(w\): the leaf scores / weights.
- \(\gamma\): penalty related to adding leaves.
- \(\lambda\): L2 penalty on leaf weights.

XGBoost also supports L1 regularization, commonly associated with the `alpha` parameter.

## Why regularize?
Without a complexity penalty, a tree might add splits that improve training loss only slightly, including splits that fit noise. The penalty encourages the model to add complexity only when it is worthwhile.

## What is special about XGBoost?
The regularization is part of the objective used while building trees and choosing splits. It is not simply a separate cleanup step after the model has been trained.

**Remember:** XGBoost minimizes prediction loss plus a penalty for model complexity.
