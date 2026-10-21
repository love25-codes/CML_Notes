# 5. Numeric Features and Decision-Tree Splits

## How does a tree split a numeric feature?

For a feature such as age, income, or tenure, the tree: 1. Sorts the
unique observed values. 2. Considers midpoints between consecutive
values as candidate thresholds. 3. Evaluates how well each threshold
separates the target classes or values. 4. Chooses a split that gives
the best impurity reduction.

For example, a rule might be `tenure <= 14.5`.

## Why are trees scale-invariant?

A tree mostly cares about the order of numeric values, not their units.
Converting income from dollars to cents does not change the ordering of
examples, so equivalent split boundaries can be found.

## Axis-aligned boundaries

A normal decision-tree split checks one feature at a time, such as
`age <= 30`. This creates horizontal/vertical boundaries in feature
space.

If the true pattern is diagonal, the tree may need many small splits---a
staircase-like boundary---to approximate it.

## Which model is better?

Neither decision trees nor linear models are always best. Trees
naturally represent rule-based, non-linear boundaries; linear models
represent linear relationships efficiently. Match the model to the
structure of the data.
