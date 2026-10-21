# 5. Silhouette Score

## What does it measure?
The silhouette score considers both:
- **Cohesion:** how close a point is to points in its own cluster.
- **Separation:** how far it is from the nearest other cluster.

For a point:

\[
s=\frac{b-a}{\max(a,b)}
\]

Here, `a` is the average distance to points in its own cluster, and `b` is the average distance to points in the nearest other cluster.

## How to interpret the score
- **Close to +1:** the point fits well inside its cluster.
- **Close to 0:** the point is near a cluster boundary.
- **Close to -1:** the point may have been assigned to the wrong cluster.

A higher average silhouette score often suggests better-separated clusters.

## Why it can help more than the elbow
Inertia measures compactness only. Silhouette also considers how separated clusters are. Check individual cluster silhouette plots too: a good overall average can hide one poor cluster.

Other measures mentioned in the lecture include the **Davies–Bouldin index** and **Gap statistic**.

**Caution:** A positive silhouette score does not prove that genuine groups exist; random noise can also receive a non-zero score.
