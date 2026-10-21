# 11. Prediction Cost and Speed-ups

## Why can KNN prediction be slow?
KNN has very little training work, but for a new prediction it may need to calculate distances to every stored training example, then identify the closest `k`.

If there are `n` training examples and `d` features, a straightforward prediction typically requires work that grows with both the dataset size and the number of features (roughly \(O(nd)\), plus neighbour selection/sorting overhead).

## What makes it expensive?
- More training examples mean more distances to calculate.
- More features mean each distance calculation does more work.
- The training examples must be stored for later use.

## What are KD-trees and Ball-trees?
They are data structures that organise examples to help search for nearby points without checking every point in many cases.

They can speed up queries in low- or moderate-dimensional data. In high dimensions, their advantage often shrinks because of the curse of dimensionality.

## Main takeaway
KNN often saves work during training but pays for it when making predictions.
