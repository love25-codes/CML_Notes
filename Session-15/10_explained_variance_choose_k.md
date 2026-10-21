# 10. Explained Variance: Choosing the Number of Components

PCA orders components by how much variance they capture. We must decide how many components, `k`, to keep.

## Explained variance ratio
For a component, its explained variance ratio is:

`component eigenvalue / sum of all eigenvalues`

It tells us what fraction of the total variance that component explains.

Using the lecture's example, eigenvalues 6 and 2 give PC1 an explained variance ratio of `6 / (6 + 2) = 75%`.

## Two ways to choose k
1. **Cumulative explained variance:** add component ratios until the total reaches a target such as 90% or 95%, then keep that many components.
2. **Scree plot:** plot the variance explained by each component. Look for an “elbow”, where adding more components gives much smaller gains.

In scikit-learn, `PCA(n_components=0.95)` requests enough components to retain approximately 95% of the training data's variance.

There is no single correct threshold for every problem. Check model performance as well as explained variance.
