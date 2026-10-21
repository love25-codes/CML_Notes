# 11. Interview Questions and Quick Recap

## 1. Gini or entropy—does the choice matter?
Both measure class impurity, but they use different formulas. They can sometimes choose different splits. The session's key point is that both are ways to measure how mixed a node is.

## 2. What does information gain measure?
It measures the reduction in entropy after a split, calculated using the weighted entropy of the child groups.

## 3. Why are trees scale-invariant?
Tree splits compare feature values with thresholds. Multiplying a feature by a positive constant preserves the order of its values, so the equivalent split can remain the same.

## 4. What does “greedy” cost us?
The algorithm chooses the best split at the current node without checking every possible complete tree. A locally best choice may not produce the globally best tree.

## 5. Why is 100% training accuracy a warning?
A deep tree may have memorised the training rows. Check performance on unseen/test data before deciding whether the model generalises.

## Key points to remember
- **Gini and entropy:** measure class impurity/uncertainty.
- **Information gain:** reduction in entropy after a split.
- **Greedy splitting:** choose the best current split and repeat.
- **Regression trees:** predict a number; leaves use the mean and splits reduce MSE.
- **Axis-aligned splits:** one feature threshold at a time.
- **Overfitting:** deep trees can memorise data and have high variance.
- **Scale invariance:** feature ordering matters more than units.
