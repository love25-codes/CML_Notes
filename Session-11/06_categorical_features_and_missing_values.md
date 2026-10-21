# 6. Categorical Features and Missing Values

## Categorical features

Categorical features represent groups rather than measurements---for
example, city, colour, or product type.

### One-hot encoding

One-hot encoding creates a separate indicator column for each category.
It is safe and widely used, but a feature with many categories (such as
20 cities) can become many columns. This may fragment the data across
many weak splits and lead to deeper, less effective trees.

### Ordinal encoding

Ordinal encoding assigns numbers to categories. It is compact, but it
introduces an order. If the assigned order does not reflect a useful
relationship, the tree may need extra splits to recover a good
separation.

### Native categorical support

The lecture mentions LightGBM and CatBoost as tools that can handle
categorical features natively, rather than requiring the same encoding
approach.

## Missing values

Some tree implementations, including the scikit-learn trees discussed in
the lecture, have historically required missing values to be imputed
first.

-   **Imputation:** Fill missing values using a chosen rule, such as a
    median for a numeric feature.
-   **Surrogate split:** Use another correlated feature as a backup when
    the preferred split feature is unavailable.
-   **Learned default direction:** XGBoost can learn which direction
    missing values should take at a node.

## Remember

Encoding choices affect how a tree can split the data. Missing-value
support depends on the particular tree implementation.
