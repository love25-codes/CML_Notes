# 4. Principal Components, Defined

A **principal component (PC)** is a new feature made by combining the original features.

For example, if a dataset has height and weight, a component might combine both values using weights. In general, each component can use all original features.

- PC1 captures the largest possible variance.
- PC2 captures the largest possible amount of remaining variance and is perpendicular to PC1.
- Components are ordered from the most variance captured to the least.
- There can be at most `min(number of rows, number of original features)` components in the usual mathematical setup.

PCA can be understood in two related ways: it finds a direction with maximum projected spread, and the corresponding line gives a least-squares representation that minimises the total squared perpendicular distances to that line.

**Important:** high variance is treated as useful information by PCA, but that assumption is not always true.
