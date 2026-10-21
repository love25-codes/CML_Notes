# 7. Linkage Criteria

Linkage tells hierarchical clustering how to measure the distance between two clusters.

| Linkage | Meaning | Typical behaviour |
|---|---|---|
| **Single** | Distance between the closest pair of points, one from each cluster | Can create long, chain-like clusters; sensitive to noise |
| **Complete** | Distance between the farthest pair of points | Often favours compact clusters |
| **Average** | Average of pairwise distances between the two clusters | A compromise between single and complete |
| **Ward** | Chooses the merge that causes the smallest increase in within-cluster variance | Often favours compact groups |

## Ward linkage and K-Means
Ward linkage is related to K-Means because both focus on within-cluster variation. However, they work differently:
- K-Means repeatedly reassigns points and updates centroids.
- Ward clustering builds a hierarchy by greedily merging clusters.

**Remember:** The linkage choice can change the shape and structure of the resulting clusters.
