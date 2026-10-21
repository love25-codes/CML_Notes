# 4. The Pruning Path and Choosing Alpha

## What is a pruning path?

As `ccp_alpha` increases, a tree usually becomes smaller in steps. It
does not necessarily change at every possible alpha value.

In scikit-learn, `cost_complexity_pruning_path()` returns the sequence
of alpha values at which the tree actually changes.

## What happens at the extremes?

-   **`alpha = 0`:** No complexity penalty; the full tree can remain.
-   **Large alpha:** More pruning; at an extreme, the tree may collapse
    to the root, which predicts the majority class in classification.

A very simple tree has high bias (it may miss real patterns) and low
variance (it changes less across training samples). A very complex tree
can have the opposite problem.

## How should alpha be selected?

Do not choose alpha just because it creates the smallest tree. Compare
candidate values using cross-validation: 1. Get candidate alpha values
from the pruning path. 2. Train/evaluate trees for those values. 3. Use
cross-validation to estimate performance on unseen data. 4. Keep the
alpha that performs best under the chosen evaluation metric.

## Remember

The goal is not the smallest tree. The goal is a tree that generalises
well to new data.
