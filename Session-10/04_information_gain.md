# 4. Information Gain

## What is information gain?
**Information gain measures how much uncertainty is reduced by a split.** A useful split creates child groups that are more class-consistent than the parent group.

Using entropy:

\[
IG=H(\text{parent})-\sum_k\frac{n_k}{n}H(\text{child}_k)
\]

- `H(parent)`: entropy before splitting.
- `H(child_k)`: entropy of child group `k`.
- `n_k`: number of examples in that child.
- `n`: total number of examples in the parent.
- `n_k/n`: the child's share of all examples.

The weighted average matters because a tiny pure child should not outweigh a large, messy child.

## Simple example
Suppose the parent has entropy `0.8`.
- Split A gives weighted child entropy `0.2`, so gain = `0.8 - 0.2 = 0.6`.
- Split B gives weighted child entropy `0.6`, so gain = `0.8 - 0.6 = 0.2`.

Split A wins because it reduces uncertainty more.

## Important detail
Information gain in this session is defined using **entropy**. Gini-based trees use a similar idea: compare parent impurity with weighted child impurity.

## Remember
**Choose the split that produces the greatest reduction in impurity.**
