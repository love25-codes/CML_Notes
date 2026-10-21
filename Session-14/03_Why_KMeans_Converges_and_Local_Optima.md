# 3. Why K-Means Converges and Local Optima

## Why does it converge?
Each K-Means iteration has two steps:

- **Assign step:** points are assigned to their nearest centroid, which cannot increase the total squared distance for the current centroids.
- **Update step:** for fixed cluster memberships, the mean is the position that minimises the sum of squared distances.

So these steps do not increase inertia. Because there are only finitely many possible assignments, the algorithm eventually stops changing assignments.

## Why only a local optimum?
The starting centroids affect the final result. K-Means can stop at a good solution near its starting point without finding the best possible grouping overall.

## How to improve the starting point
- **K-Means++** chooses spread-out initial centroids to help produce better starts.
- **Multiple initialisations** (for example, `n_init=10`) run the algorithm from different starts and keep the run with the lowest inertia.

## Scaling features
K-Means uses Euclidean distance. If one feature has much larger numeric values than another, it can dominate the distance. Scale features before clustering when their units or ranges differ.

**Remember:** Convergence means the process has stopped improving; it does not prove the result is globally best or meaningful.
