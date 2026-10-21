# 9. Extra Trees and the Cost of a Forest

## What are Extra Trees?
The session describes Extra Trees as a cousin of Random Forest. In addition to randomising the feature subset, Extra Trees also choose split thresholds randomly.

This can decorrelate trees even further. The trade-off described in the session is a little more bias and a little less variance.

## What do we gain with a forest?
- More stable predictions than relying on one high-variance tree.
- Often improved predictive accuracy.

## What do we give up?
A single decision tree can be followed from root to leaf to explain one prediction. A forest of hundreds of trees is much harder to explain in that same simple way.

The session's example is 300 trees: accuracy and stability may improve, but the model is no longer as easy to interpret as one tree.

## Remember
More trees can improve stability, but the whole forest is less directly interpretable than an individual decision tree.
