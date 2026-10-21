# 14. PCA for Visualisation

When a dataset has many features, we cannot plot it directly on a normal 2-D graph. PCA can transform the data into two principal components, which can be plotted as horizontal and vertical axes.

A common exploratory step is:
1. Fit PCA on training data (or use an appropriate exploratory workflow without contaminating later evaluation).
2. Transform observations to two components.
3. Plot the points and colour them by class/category.
4. Look for visible patterns or separation.

If classes separate clearly, that can be an encouraging sign. If they overlap, the task may be harder, but overlap in a 2-D PCA plot does not prove that a model cannot learn the classes.

The lecture also mentions **t-SNE** and **UMAP** as visualisation methods. They can be useful for exploratory plots, but the lecture cautions against treating their visual layouts as a stable modelling transformation for unseen data.
