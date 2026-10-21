# 10. Practical Choices: Metric, K, and Weighted Neighbours

## Choose k with cross-validation
Try several `k` values and evaluate them on validation folds. Pick the value that performs well on data not used to make that particular prediction.

## Use an odd k for two-class voting
For binary classification, an odd `k` often reduces the chance of a tie between the two classes. Ties can still happen in some situations, depending on the voting setup.

## Choose a distance metric that suits the data
The lecture's practical guidance:
- **Euclidean:** a common default for numerical features.
- **Manhattan:** worth trying in higher-dimensional settings.
- **Cosine:** useful for text or vector representations where direction matters.

Do not treat any metric as universally best; validate the choice.

## Distance-weighted voting
Ordinary KNN gives each of the `k` neighbours one vote. Distance-weighted KNN gives closer neighbours more influence.

A simple weighting idea is:

\[
w = \frac{1}{d}
\]

where `d` is the neighbour's distance. In this setup, a closer point gets a larger weight, while a distant point gets a smaller weight. Implementations may handle zero distances specially.

## Why use weights?
A point barely inside the chosen neighbourhood should not necessarily have as much influence as a point extremely close to the query. Distance weighting makes the vote less equal between near and far neighbours.

## Main takeaway
Tune `k`, choose a suitable distance metric, and consider weighting votes by distance.
