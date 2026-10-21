# 10. Would Bagging Help Linear Regression?

## The discussion question
The session asks: “Would bagging meaningfully improve a linear regression model?”

## How to reason about it
Bagging mainly reduces **variance**. So ask:
1. Does the base model have substantial variance?
2. Would different bootstrap samples cause its predictions to change significantly?
3. Is variance the main problem, or is the model too biased for the pattern in the data?

If a model does not have much variance to reduce, bagging may provide little benefit. If the main problem is bias, bagging is not designed to solve that problem.

## Compare with decision trees
The session emphasises that deep decision trees are high-variance learners, which makes them especially suitable for bagging.

## Takeaway
Do not assume bagging improves every model equally. Its usefulness depends on how much variance the base learner has.
