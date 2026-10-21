# 7. How PCA Works: Five Main Steps

## Step 1: Centre the data
Subtract each feature's mean from its values. This makes each feature's average zero.

## Step 2: Calculate the covariance matrix
The covariance matrix describes each feature's variance and how pairs of features vary together. For centred data `X`, the sample covariance matrix is often written as:

`Σ = XᵀX / (n − 1)`

where `n` is the number of rows.

## Step 3: Find eigenvectors and eigenvalues
- **Eigenvectors** give the principal directions (the new axes).
- **Eigenvalues** tell how much variance lies along those directions.

They satisfy the equation `Σv = λv`.

## Step 4: Sort the components
Sort the eigenvalues from largest to smallest, and put their eigenvectors in the same order.

## Step 5: Choose and project
Keep the first `k` components and project the centred data onto them. The result has `k` dimensions instead of the original number.

Many software implementations use Singular Value Decomposition (SVD) to calculate PCA reliably.
