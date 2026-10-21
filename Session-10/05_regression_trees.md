# 5. Regression Trees

## What is a regression tree?
A classification tree predicts a category, such as `approved` or `rejected`. A **regression tree predicts a number**, such as a house price.

## What does a leaf predict?
In this session, each leaf predicts the **mean (average)** of the target values belonging to that leaf.

For example, if a leaf contains house prices of ₹20 lakh, ₹24 lakh, and ₹25 lakh, its prediction is:

`(20 + 24 + 25) / 3 = 23 lakh`

## How does it choose a split?
The tree tries splits and looks for ones that reduce the mean squared error (MSE).

\[
MSE_{\text{node}}=\frac{1}{n}\sum_{i\in\text{node}}(y_i-\bar y_{\text{node}})^2
\]

- `y_i`: an actual target value.
- `ȳ_node`: the average target value in the node.
- `n`: number of examples in the node.

MSE measures the average squared distance between actual values and the node's mean. Lower MSE means values are closer to their average.

## Why use the mean?
The mean is the constant prediction that minimises squared error for the examples in that leaf. The tree's main task is to find a useful way to divide the data into leaves.

## Remember
**Regression tree → numeric prediction; leaf prediction → mean; split goal → reduce MSE.**
