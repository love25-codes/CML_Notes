# 10. What to Do When Feature Importance Looks Suspicious

## Example question

A feature-importance chart ranks `customer_id` as the second most
important feature. What might have happened?

## Step 1: Check which measure was used

If the ranking came from MDI (`feature_importances_`), the ID may look
important because it has many possible split points. The tree may have
found a pattern that works in the training data by chance.

## Step 2: Check permutation importance

Measure the baseline validation score, shuffle only the ID column, and
score again.

-   If the score barely changes, the model does not rely much on the ID
    for validation predictions.
-   If the score drops substantially, the model relies on that column in
    the evaluated data---but this still does not prove the ID causes the
    outcome. Check for leakage or data-specific patterns.

## Step 3: Remember correlated features

If two features carry similar information, permutation importance may
understate either one individually because the other can compensate.

## Main lesson

A disagreement between MDI and permutation importance can reveal a
weakness in the original ranking. Feature importance is about a model's
predictive behaviour, not proof of cause and effect.
