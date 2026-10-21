# 5. Out-of-Bag (OOB) Samples and OOB Score

## What are OOB samples?
For each tree, some training rows are left out of that tree's bootstrap sample. These rows are called **out-of-bag (OOB) samples** for that tree.

The session's 63.2% rule means roughly 36.8% of rows are left out of any one bootstrap sample.

## How can OOB estimate performance?
For a particular training row:
1. Find the trees whose bootstrap samples did **not** include that row.
2. Collect predictions from only those trees.
3. Combine those predictions to estimate the row's outcome.
4. Compare the predictions with the known outcome across rows to estimate model performance.

Each row is evaluated using trees that did not train on it.

## Why is it useful?
OOB gives a cross-validation-like estimate without requiring a separate validation run. In scikit-learn, the session refers to enabling it with `oob_score=True`.

## Important detail
A row is OOB for some trees, not necessarily for every tree. Its OOB prediction is based only on the trees that excluded it.
