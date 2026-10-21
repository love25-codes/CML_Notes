# 17. Interview Questions and Simple Answers

## 1. What do eigenvectors and eigenvalues represent in PCA?
Eigenvectors give the principal directions or new axes. Eigenvalues tell how much variance is captured along each direction.

## 2. Why is centring important?
Centring subtracts the mean so PCA studies spread around the data's centre instead of being distracted by its position relative to the origin.

## 3. Why might we standardise?
Features with large numerical scales can dominate PCA. Standardisation makes differently scaled features more comparable.

## 4. How is PCA different from linear regression?
PCA finds directions of maximum variance without a target column. Linear regression predicts a target and minimises errors in that target direction.

## 5. Why is fitting PCA before splitting data leakage?
Because PCA learns components from all the data, including the future test set. Split first and fit PCA only on training data.

## 6. When might you avoid PCA?
Avoid or reconsider PCA when individual feature interpretation is essential, when low-variance information may be important, or when validation shows that PCA hurts model performance.
