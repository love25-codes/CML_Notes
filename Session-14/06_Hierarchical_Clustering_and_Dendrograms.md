# 6. Hierarchical Clustering and Dendrograms

## What is hierarchical clustering?
In the agglomerative approach described in the lecture:
1. Start with every data point as its own cluster.
2. Merge the two closest clusters.
3. Keep merging clusters.
4. Eventually, all points form one cluster.

Unlike K-Means, you can build the hierarchy before choosing the final number of clusters.

## What is a dendrogram?
A dendrogram is a tree diagram showing which clusters were merged and at what distance.

- The leaves at the bottom represent individual points.
- The height of a merge represents the distance at which groups were joined.
- A **horizontal cut** across the tree gives a set of clusters.

To estimate K, draw a horizontal line across the dendrogram and count the separate branches it crosses. A large vertical gap between merges may suggest a useful cut.

## Advantages
- Shows nested groupings at different levels.
- Does not require fixing K before building the hierarchy.
- For a fixed distance definition and tie handling, the procedure is deterministic.

**Remember:** The result depends on the distance measure and linkage criterion.
