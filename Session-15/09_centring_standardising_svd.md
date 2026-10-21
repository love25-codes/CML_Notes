# 9. Centring, Standardising, and SVD

## Centring is important
Centring means subtracting each feature's mean. PCA is intended to study variation around the centre of the data. Without centring, the first direction can be strongly affected by how far the data sits from the origin rather than by its spread.

## Why standardise?
PCA looks for directions with high variance. If one feature is measured in rupees and another in years, the feature with larger numerical units may dominate the result.

Standardisation usually means subtracting the mean and dividing by the standard deviation, giving each feature a comparable scale. It is commonly recommended when features use different units. If all features share a meaningful, comparable unit, standardisation may not always be necessary.

## What is SVD?
**Singular Value Decomposition (SVD)** is a numerical method often used to calculate PCA. It helps compute the principal directions robustly.

**Practical reminder:** fit the scaler using training data only, then apply that same scaler to validation/test data.
