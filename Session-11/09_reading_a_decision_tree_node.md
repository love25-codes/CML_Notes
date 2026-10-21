# 9. Reading a Decision-Tree Node

A tree plot can explain an individual prediction by showing the rules
followed from the root to a leaf.

The lecture's example node is:

-   `tenure <= 14.5`
-   `gini = 0.42`
-   `samples = 380`
-   `value = [268, 112]`
-   `class = stays`

## What each field means

-   **Rule (`tenure <= 14.5`):** If tenure is 14.5 months or less,
    follow the left branch; otherwise, follow the other branch.
-   **Gini (`0.42`):** A measure of how mixed the classes are at this
    node. A lower value means the node is more dominated by one class;
    zero means all samples belong to one class.
-   **Samples (`380`):** 380 training examples reached this node.
-   **Value (`[268, 112]`):** There are 268 examples in one class and
    112 in the other, in the order used by the tree.
-   **Class (`stays`):** The node's predicted class, typically the
    majority class at that node.

## How to explain one prediction

Start at the root and check the test example against each rule. Follow
the matching branch until reaching a leaf. The path gives a
human-readable explanation of how the tree arrived at its prediction.

## Important caution

This explains the model's decision path. It does not automatically prove
that the features caused the outcome.
