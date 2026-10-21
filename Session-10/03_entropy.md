# 3. Entropy

## What is entropy?
**Entropy measures uncertainty or class-mixing in a node.** A pure node has no uncertainty; a node with a 50/50 mix of two classes has the highest uncertainty for two classes.

Formula:

\[
H=-\sum_{i=1}^{c}p_i\log_2(p_i)
\]

`p_i` is the fraction of examples in class `i`. A term with `p_i = 0` is treated as contributing 0.

## Examples for two classes
- **100% / 0%:** entropy = `0` bits.
- **90% / 10%:** entropy is about `0.47` bits.
- **50% / 50%:** entropy = `1` bit.

## Why are bits mentioned?
Entropy can be understood as the average amount of information, in bits, needed to describe a randomly chosen example's class when the class proportions are known. If every example has the same class, there is no uncertainty to resolve.

## Entropy and log-loss
The session connects entropy with cross-entropy/log-loss used in logistic regression: they are related measures of surprise. Logistic regression changes model weights, while a decision tree partitions examples into groups.

## Remember
**Pure node → entropy 0.** For two classes, **50/50 → entropy 1 bit**.
