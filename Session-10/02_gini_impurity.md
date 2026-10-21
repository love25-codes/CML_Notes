# 2. Gini Impurity

## What is Gini impurity?
**Gini impurity measures how mixed the classes are inside a node.** A node containing only one class has Gini impurity 0. A node with an even mix of two classes has Gini impurity 0.5.

Formula:

\[
\text{Gini}=1-\sum_{i=1}^{c}p_i^2
\]

Here, `p_i` is the fraction of examples belonging to class `i`, and `c` is the number of classes.

## Examples for two classes
- **100% / 0%:** `1 - 1² - 0² = 0` — completely pure.
- **90% / 10%:** `1 - 0.9² - 0.1² = 0.18` — mostly one class.
- **50% / 50%:** `1 - 0.5² - 0.5² = 0.50` — most mixed.

## Intuition
Imagine randomly choosing an example from a node and guessing its label using the node's class proportions. Gini impurity represents the chance of a wrong guess under this interpretation.

Lower Gini means the classes are less mixed. Higher Gini means they are more mixed. For `c` classes, the maximum is `1 - 1/c`.

## How is it used?
A classification tree compares candidate splits and prefers the split that gives the children the lowest weighted impurity (equivalently, the greatest impurity reduction).

## Remember
**Pure node → Gini 0.** For two classes, **50/50 → Gini 0.5**.
