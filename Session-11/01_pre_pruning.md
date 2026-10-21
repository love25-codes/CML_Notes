# 1. Pre-Pruning (Stopping a Tree Early)

## What is it?

Pre-pruning means stopping a decision tree from growing too much while
it is being built. Instead of letting the tree learn every small detail
in the training data, we set limits in advance.

This helps prevent **overfitting**: when a model memorises training
examples but performs poorly on new examples.

## Common pre-pruning controls

-   **`max_depth`**: Sets the maximum number of levels the tree can
    grow. This is often the first parameter to try.
-   **`min_samples_split`**: A node must contain at least this many
    samples before it can be split.
-   **`min_samples_leaf`**: Each leaf must contain at least this many
    samples.
-   **`max_leaf_nodes`**: Limits the total number of leaf nodes.
-   **`min_impurity_decrease`**: A split is allowed only if it reduces
    impurity by at least a chosen amount.

## Simple example

Imagine a tree predicting whether a student passes an exam. A very deep
tree might create rules for tiny groups, such as students who studied on
a particular day and sat in a particular row. These rules may fit the
training data by chance.

Setting `max_depth=3`, for example, limits how many levels the tree can
use.

## Advantages and limitation

-   It is quick and simple.
-   It can reduce overfitting.
-   But it may stop too early. A split that looks unhelpful now could
    lead to useful splits farther down the tree.

## Remember

**Pre-pruning = stop early.** The lecture notes say `max_depth` alone
often provides much of the benefit.
