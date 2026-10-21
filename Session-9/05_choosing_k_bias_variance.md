# 5. Choosing K: Bias and Variance

The value of `k` controls how complex or smooth KNN's decision boundary is.

## What is bias?
**Bias** is error caused by a model being too simple to capture the real pattern.
- High bias: the model may miss important patterns.
- In KNN, a very large `k` tends to smooth over local differences and can have high bias.

## What is variance?
**Variance** means the model changes a lot when the training data changes slightly.
- High variance: the model reacts strongly to individual examples or noise.
- In KNN, `k = 1` can create a very jagged boundary and tends to have high variance.

## How K changes the balance
- **Small k (especially k = 1):** low bias, high variance.
- **Moderate k:** may give a useful balance.
- **Large k:** higher bias, lower variance.
- **k = n:** every training example votes, so the classifier always predicts the overall majority class (assuming ordinary unweighted voting).

## Why does 1-NN have zero training error?
For a training point, its closest training point is normally itself, at distance zero. It therefore receives its own label when `k = 1`. So the training accuracy is 100% in the standard setup.

But this does **not** guarantee good performance on unseen data. It can memorise noise and overfit.

## How should you choose k?
Use **cross-validation**: try several values of `k`, compare their validation performance, and choose a value that works well on data not used for fitting.

For binary classification, an odd `k` can help avoid ties, although it does not guarantee that ties are impossible in every situation.

## Main takeaway
`k` is a **bias–variance dial**: small values are sensitive; large values are smoother.
