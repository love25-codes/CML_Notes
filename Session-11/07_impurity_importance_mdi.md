# 7. Impurity-Based Feature Importance (MDI)

## What is MDI?

MDI stands for **Mean Decrease in Impurity**. In scikit-learn,
`feature_importances_` reports how much each feature contributes to
reducing impurity across the tree, weighted by the number of samples
reaching each split.

In simple words, it adds up the impurity reduction credited to each
feature.

## Three important traps

### 1. Importance is not causality

A feature can be useful for prediction because it acts as a proxy for
another variable. That does not mean it causes the outcome.

### 2. Cardinality bias

Continuous features and ID-like columns offer many possible split
points. They may look important by chance, even when they do not contain
a meaningful general pattern.

### 3. Correlated features split the credit

If two features carry similar information, the tree may use both. Their
importance scores can share the credit, making each one look less
important than the underlying signal really is.

## Example: customer ID

A random `customer_id` might rank highly under MDI because it offers
many possible split points. That high score does not prove that the ID
has a useful relationship with whether a customer stays.

## Remember

MDI is convenient, but do not treat its ranking as unquestionable
evidence about which features truly matter.
