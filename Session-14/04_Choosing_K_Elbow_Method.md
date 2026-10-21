# 4. Choosing K: The Elbow Method

## What is the elbow method?
Run K-Means with several values of K and plot **K against inertia**.

Inertia generally decreases as K increases because more clusters allow points to sit closer to their centroids.

## How to read the plot
Look for an “elbow”: a point where increasing K further gives much smaller improvements in inertia.

For example, if inertia drops a lot from K=1 to K=3 but only a little after K=3, K=3 may be a reasonable choice.

## Limitation
Real data often produces a smooth curve with no clear elbow. This does not necessarily mean you did something wrong.

**Remember:** Do not simply choose the K with the smallest inertia. At K equal to the number of points, inertia can become zero, which is not a useful general solution.
