# 7. Why Feature Scaling Is Mandatory for KNN

KNN compares examples using distances. If one feature has much larger numerical values than another, it can dominate the distance calculation—even if it is not more important.

## Example from the lecture
Imagine two people differ by:
- Age: 20 years
- Income: ₹5,000

With squared differences in Euclidean distance:
- Age contributes \(20^2 = 400\)
- Income contributes \(5000^2 = 25{,}000{,}000\)

The income difference overwhelms the age difference numerically. KNN may behave as if income is vastly more important simply because it is measured on a larger scale.

## What is feature scaling?
Feature scaling changes numerical features to comparable scales. Common methods include:
- **Standardisation:** subtract the feature mean and divide by its standard deviation.
- **Min-max scaling:** map values to a chosen range, often 0 to 1.

These methods are general background explanations; the key point in the lecture is that scaling prevents units from silently deciding feature influence.

## Why it matters
Without scaling, changing a feature from dollars to cents could drastically change the distance and the neighbours, even though the underlying information is the same.

## Practical tip
Fit the scaler using the training data only, then apply that fitted scaler to validation/test data. In practice, put scaling and KNN together in a machine-learning pipeline to avoid data leakage.

## Main takeaway
**Scale features before using distance-based KNN.** Otherwise, large-number features can dominate by accident.
