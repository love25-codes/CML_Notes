# 8. The Curse of Dimensionality

A **dimension** is one feature or coordinate. If a dataset has age and income, it has two dimensions. If it has 100 measured features, it has 100 dimensions.

## What is the curse of dimensionality?
As the number of dimensions grows, the space that data can occupy grows extremely quickly. With the same amount of data, points become sparse and it becomes harder for KNN to find genuinely close neighbours.

## Why does “local” stop being local?
The lecture gives an illustration for capturing 1% of the data: the fraction of each axis that must be spanned is approximately

\[
r^{1/d}
\]

where `r = 0.01` is the fraction of space/data being considered in the illustration and `d` is the number of dimensions.

As shown in the lecture:
- 2 dimensions: about 0.10 of each axis
- 10 dimensions: about 0.63
- 100 dimensions: about 0.95

So in 100 dimensions, the region may need to span about 95% of every axis to cover that small fraction under the lecture's illustration. The neighbourhood is no longer very local.

## Why does this hurt KNN?
KNN relies on the idea that nearby points are meaningfully similar. In high dimensions, data becomes sparse and distances become less informative. “Nearest” may not mean much more similar than “far away.”

## What can help?
- Remove irrelevant or redundant features.
- Use feature selection.
- Reduce dimensions, for example with PCA when appropriate.
- Compare validation performance rather than assuming more features are better.

## Main takeaway
More features are not always better. High-dimensional data can make nearest-neighbour comparisons unreliable.
