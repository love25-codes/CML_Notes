# 9. Quick Revision and Practice

## Key ideas
- **Clustering:** grouping similar data without pre-existing labels.
- **Cohesion:** points within a cluster are close.
- **Separation:** different clusters are far apart.
- **K-Means:** assign points to nearest centroids, then update centroids to their means.
- **Inertia:** total squared distance from points to their assigned centroids.
- **Elbow method:** look for where additional clusters give diminishing returns.
- **Silhouette:** combines within-cluster closeness and separation from the nearest other cluster.
- **Dendrogram:** tree showing hierarchical merges; a horizontal cut selects clusters.
- **Linkage:** rule for measuring distance between clusters.
- **Ward linkage:** merges clusters with the smallest increase in within-cluster variance.

## Practice questions
1. Why does K-Means usually stop changing?
2. Why can K-Means converge to a local rather than global solution?
3. Why should you scale features before using K-Means?
4. Why does inertia decrease as K increases?
5. What do silhouette scores near +1, 0, and -1 mean?
6. How do you choose a cut on a dendrogram?
7. How do single, complete, average, and Ward linkage differ?
8. Why can clustering random noise be misleading?
9. What would make a cluster useful to a domain expert?

## Short answers
1. Each step does not increase inertia, and there are finitely many assignments.
2. The result depends on the initial centroids.
3. Large-scale features can dominate distance calculations.
4. More clusters let points be closer to their own centroids.
5. Good fit; boundary; likely misassignment, respectively.
6. Cut horizontally and count the branches crossed.
7. They use closest, farthest, average, or variance-increase criteria.
8. Algorithms can always produce groupings, even without real structure.
9. It has a clear, describable distinction and supports a useful decision.

## Final takeaway
Clustering is exploratory. Always ask whether the groups are stable, separated, interpretable, and genuinely useful.
