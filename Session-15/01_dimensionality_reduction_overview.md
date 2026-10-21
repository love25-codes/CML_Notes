# 1. Dimensionality Reduction: Overview

## What does it mean?
A dataset has **features** (columns). For example, a student dataset may contain age, attendance, marks, study hours, and many other columns. The number of features is called the **dimensionality** of the data.

**Dimensionality reduction** means representing data using fewer features while trying to keep the most useful information.

## Why do we use it?
- Too many features can make a model slower.
- Some features contain repeated or similar information.
- Some features may mostly contain noise.
- High-dimensional data can make distance-based methods such as KNN less effective.
- We may want to show complex data in two dimensions.

## What is PCA?
**Principal Component Analysis (PCA)** is a method that creates new features from the original features. It keeps the directions in which the data varies most, and we can keep only the most useful directions.

**Remember:** PCA reduces the number of dimensions by transforming features, not simply by deleting selected columns.
