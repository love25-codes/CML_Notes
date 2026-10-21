# 9. Distance Concentration and PCA

## What is distance concentration?
In high-dimensional spaces, the difference between the nearest and farthest distances can become small relative to the distances themselves. Distances start to look more alike.

The lecture expresses this idea with the ratio:

\[
\frac{d_{\max}-d_{\min}}{d_{\min}} \longrightarrow 0
\]

Here:
- \(d_{\max}\) = distance to the farthest point in the considered set
- \(d_{\min}\) = distance to the nearest point

The ratio approaching zero means the gap becomes small compared with the nearest distance.

## Why is that a problem?
KNN depends on ranking points by distance. If almost all distances are similar, the “nearest” point may not be meaningfully closer than other points. The neighbourhood becomes less useful for prediction.

## How does PCA relate?
**PCA (Principal Component Analysis)** is a technique that transforms data into a smaller set of directions that capture much of its variation. It can reduce the number of dimensions before KNN is applied.

PCA is not a guaranteed fix: the reduced representation must still preserve information useful for the prediction task, and its performance should be evaluated.

## Main takeaway
Distance concentration helps explain why KNN can struggle in high dimensions and why dimensionality reduction may help.
