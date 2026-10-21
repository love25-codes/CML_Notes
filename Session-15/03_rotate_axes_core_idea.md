# 3. Rotate the Axes: The Core Idea

Imagine points on a graph that form a long, slanted cloud. The usual horizontal and vertical axes may not describe the cloud efficiently.

PCA finds new axes that match the data's shape:
- **PC1 (first principal component):** the direction with the greatest variance, or spread.
- **PC2 (second principal component):** the direction with the greatest remaining variance, at a right angle to PC1.
- Later components continue in the same way, each perpendicular to the earlier ones.

PCA first changes the coordinate system. **Compression happens when we choose to keep only some of the new axes.** If we keep fewer components, we use fewer numbers to represent each data point, but some information is lost.
