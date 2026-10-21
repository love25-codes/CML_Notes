# 8. When Not to Cluster

## The central warning
An algorithm returning clusters does not mean the data contains real, useful groups.

For example, K-Means can divide completely random data into four clusters and still return a non-zero silhouette score. It does not automatically recognise that the data may be pure noise.

## Situations where K-Means can struggle
- Clusters have curved or unusual shapes, such as two interleaving crescents.
- Cluster sizes or densities differ greatly.
- Features have very different scales and were not scaled.
- Data has many dimensions.
- The data has no genuine grouping structure.

K-Means tends to prefer round, similarly sized clusters and assigns every point to a cluster.

## How to judge whether clusters are useful
1. Inspect plots and cluster summaries.
2. Compare more than one evaluation measure.
3. Check whether the result is stable under reasonable changes.
4. Ask a domain expert whether each cluster can be described meaningfully.

If no one can explain what makes a group distinct or use it for a real decision, the clustering may not be actionable.

**Remember:** A tidy plot and a good score are not proof that meaningful groups exist.
