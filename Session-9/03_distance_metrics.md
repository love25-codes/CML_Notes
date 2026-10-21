# 3. Distance Metrics

A **distance metric** is a rule for measuring how far apart two data points are. KNN uses distance to decide which examples are neighbours.

Suppose two points are `x = (x₁, x₂, ...)` and `y = (y₁, y₂, ...)`.

## Euclidean distance (L2)
This is the familiar straight-line distance.

Formula:

\[
d(x,y)=\sqrt{\sum_i (x_i-y_i)^2}
\]

In two dimensions, it is like measuring the straight line between two dots.

**Example:** From `(3, 4)` to `(3, 2)`:

\[
d=\sqrt{(3-3)^2+(4-2)^2}=\sqrt{4}=2
\]

## Manhattan distance (L1)
This adds the absolute differences across features:

\[
d(x,y)=\sum_i |x_i-y_i|
\]

Think of moving along city blocks: you travel horizontally and vertically rather than diagonally.

For `(3, 4)` and `(3, 2)`, the Manhattan distance is `|3-3| + |4-2| = 2`.

## Minkowski distance (Lp)
This is a family of distance measures:

\[
d(x,y)=\left(\sum_i |x_i-y_i|^p\right)^{1/p}
\]

Different values of `p` give different distance behaviours. `p = 1` gives Manhattan distance; `p = 2` gives Euclidean distance.

## Other metrics mentioned in the lecture
- **Cosine distance/similarity:** useful for comparing the direction of vectors, often used with text. Two documents can be similar in word usage direction even if one is longer.
- **Hamming distance:** counts positions that differ, useful for categorical strings or binary features.
- **L-infinity distance:** looks at the largest absolute difference in any one feature.

## Which should you choose?
The lecture suggests Euclidean as a common default, Manhattan as something to consider in higher dimensions, and cosine for text. The best choice still depends on the data and should be checked empirically.

## Main takeaway
The distance formula affects who counts as a neighbour—so it can change KNN's prediction.
