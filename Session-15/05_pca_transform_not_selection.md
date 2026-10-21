# 5. PCA: Transformation, Not Feature Selection

PCA does **not** usually choose a few original columns and throw away the rest. Instead, it builds new columns called principal components.

Example: original features are `height`, `weight`, and `age`. A principal component could be a weighted combination of all three.

This is different from **feature selection**, which keeps some original columns and removes others. The lecture contrasts PCA with methods such as Lasso, which can select features.

### A caution
PCA prefers directions with high variance. But a feature with low variance may still be important for separating categories or predicting an outcome. So, PCA can sometimes remove useful information.

**Exam tip:** PCA transforms features; feature selection selects features.
