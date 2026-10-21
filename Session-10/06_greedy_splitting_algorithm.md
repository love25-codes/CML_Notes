# 6. The Greedy Splitting Algorithm

## How does a tree choose a question?
At each node, the algorithm:
1. Looks at each feature.
2. Tries candidate thresholds for that feature.
3. Splits the examples into child groups.
4. Measures the weighted impurity of those children.
5. Keeps the split with the largest impurity reduction.
6. Repeats the process for each child.

The process stops when a stopping condition is met—for example, the node is pure or a configured limit is reached.

## What does “greedy” mean?
A greedy algorithm chooses what looks best **right now**. It does not consider every possible future tree and does not go back to change earlier choices.

## Why can that be a problem?
A split that looks best immediately may not lead to the best overall tree. Another first split might have allowed better splits later. The greedy algorithm does not explore all those possibilities.

Finding a globally optimal decision tree is computationally hard (the session describes it as NP-hard), so practical tree algorithms use this greedy approach.

## Remember
**Try splits → score them → choose the best current split → repeat on children.**
