# 13. Bias–Variance Trade-off and Decision Boundaries

## What is a decision boundary?
For a classification model, a decision boundary is the line or region separating areas where the model predicts different classes.

## How K changes the boundary
- **K = 1:** the boundary can be jagged and closely follow individual data points.
- **Larger K:** the boundary usually becomes smoother because each prediction considers more neighbours.

## Connect this to bias and variance
- A jagged boundary often indicates high variance: small changes in the data can change the prediction.
- A very smooth boundary may miss local patterns, indicating higher bias.

The goal is not automatically to choose the smallest or largest `k`; it is to find a balance that works on unseen examples.

## What happens when noise features are added?
An irrelevant feature can affect distances even though it contains no useful signal. As more irrelevant dimensions are added, KNN's accuracy can fall. This is one way to see the curse of dimensionality in practice.

## Main takeaway
Visualise the boundary if possible, but use validation performance to decide whether a value of `k` generalises well.
