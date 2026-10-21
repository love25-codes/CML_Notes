# 8. Eigenvalues and Eigenvectors: Worked Example

Suppose the covariance matrix for two features is:

`Σ = [[4, 2], [2, 4]]`

The diagonal values, 4 and 4, mean both features have variance 4. The off-diagonal values, 2, show positive covariance.

## Step 1: Find the eigenvalues
Solve `det(Σ − λI) = 0`. For this matrix:

`(4 − λ)² − 2² = 0`

This gives eigenvalues `λ₁ = 6` and `λ₂ = 2`.

## Step 2: Interpret the directions
- The eigenvector for eigenvalue 6 points along `(1, 1)`, meaning the direction where the two features increase together.
- The eigenvector for eigenvalue 2 points along `(1, −1)`, perpendicular to the first direction.

## Step 3: Calculate explained variance
Total variance is `6 + 2 = 8`. PC1 captures `6 / 8 = 0.75`, or **75%** of the variance. PC2 captures the remaining 25%.

So, keeping only PC1 reduces two dimensions to one while retaining 75% of the total variance. It loses 25% of the variance, so whether this is acceptable depends on the task.
