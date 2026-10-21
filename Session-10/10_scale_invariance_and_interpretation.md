# 10. Scale Invariance and Reading a Tree

## Why don't trees usually need feature scaling?
A tree asks comparisons such as `age < 30`. If every age is multiplied by 1,000, the equivalent threshold becomes `age < 30000`; the order of the values stays the same.

Because the ordering is unchanged, the same partition can be chosen. This is why decision trees are described as scale-invariant in the session.

## How to explain a prediction
Start at the root and follow the branch matching each answer. Continue until reaching a leaf. Then explain the sequence of rules in plain English.

Example:
1. Age is greater than 30.
2. Income is greater than ₹50,000.
3. The leaf predicts Class 1.

This path gives a human-readable reason for the prediction, based on the tree's learned rules.

## Remember
**Scaling a feature by a positive factor preserves its ordering.** And a tree's prediction can be explained by tracing root → branches → leaf.
