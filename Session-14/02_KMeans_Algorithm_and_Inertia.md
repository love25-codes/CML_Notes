# 2. K-Means Algorithm and Inertia

## What is K-Means?
K-Means divides data into **K groups**. Each group is represented by its **centroid**—the average position of the points assigned to that group.

You choose K before running the algorithm.

## How it works
1. Choose K and initialise K centroids.
2. **Assign:** assign every point to its nearest centroid.
3. **Update:** move each centroid to the mean of the points assigned to it.
4. Repeat Assign and Update until assignments stop changing (or the algorithm reaches its stopping limit).

## Inertia
Inertia measures how close points are to their own cluster's centroid. It is the total of the squared distances from each point to its assigned centroid.

\[
J=\sum_{k=1}^{K}\sum_{x\in C_k}\|x-\mu_k\|^2
\]

- \(C_k\): points in cluster k
- \(\mu_k\): centroid of cluster k
- Smaller inertia means tighter clusters, but it does **not** automatically mean the clustering is meaningful.

## Tiny example
For points `1, 2, 3, 10, 11, 12`, K = 2 could naturally give:
- Cluster 1: `1, 2, 3` (centroid = 2)
- Cluster 2: `10, 11, 12` (centroid = 11)

## When K-Means works best
It tends to work best when clusters are roughly round/spherical and have similar sizes and densities.

**Remember:** K-Means needs K in advance and uses distance, so feature scales matter.
