# 18. Session Recap

## Three key ideas
1. Eigenvectors are directions; eigenvalues measure variance along those directions.
2. Explained variance helps decide how many components to keep.
3. The safe workflow is: **split → scale → PCA → model**.

## Two things to remember
- PCA transforms original features into new components; it does not simply select original columns.
- Fit scaling and PCA on training data only.

## One final thought
PCA is a tool, not a guarantee of better results. Choose the number of components and decide whether to use PCA based on the task, interpretability needs, and evaluation on data that was not used to fit preprocessing.
