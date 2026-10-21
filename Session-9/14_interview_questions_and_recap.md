# 14. Interview Questions and Session Recap

## Interview-style questions

### 1. Why is KNN called a lazy learner?
Because it mostly stores the training data and delays distance calculations until prediction time.

### 2. How does K trade bias against variance?
Small `k` tends to have low bias and high variance. Large `k` tends to have higher bias and lower variance.

### 3. Why must features be scaled?
Because KNN uses distances, and features with large numerical ranges can dominate the distance calculation.

### 4. Why does KNN struggle in high dimensions?
Data becomes sparse, and distances can become less informative or more similar to one another. Finding a meaningful local neighbourhood becomes harder.

### 5. What can you do about the curse of dimensionality?
Try feature selection, remove irrelevant features, or consider dimensionality reduction such as PCA. Validate whether the change helps.

## Quick recap
Remember these points:
1. KNN predicts from the nearest stored examples.
2. Distance metrics decide what “near” means.
3. `k` controls how many neighbours vote.
4. Scaling is important before distance calculations.
5. `k = 1` has zero training error in the standard setup, but may overfit.
6. High dimensions can make distances less useful.
7. KNN's training is light, but prediction can be costly.

## One question to think about
KNN keeps all features and stored examples available for its distance calculations. What if a model could choose only a few useful features at each decision? A decision tree is one way to approach prediction differently.
