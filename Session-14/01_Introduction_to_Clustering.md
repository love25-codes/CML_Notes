# 1. Introduction to Clustering

## What is clustering?
Clustering is a machine-learning technique that groups data points that are similar to one another. It is part of **unsupervised learning**: the data does not come with correct group labels.

**Example:** A shop may group customers by shopping behaviour without being told beforehand which customer belongs to which group.

## What makes a good cluster?
- **Cohesion:** points inside the same cluster are close to each other.
- **Separation:** different clusters are far apart from one another.

Clustering methods balance these two ideas in different ways.

## Where is it useful?
- Customer segmentation
- Grouping similar documents
- Finding unusual data points (anomaly detection)
- Image compression

## Important difference from supervised learning
There is usually no known correct answer or ordinary accuracy score. We must judge whether the groups are useful and meaningful.

**Remember:** An algorithm can create groups even when the data has no real groups.
