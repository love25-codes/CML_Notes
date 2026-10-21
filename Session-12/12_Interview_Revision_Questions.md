# 12. Interview and Revision Questions

Try answering these without looking at the earlier notes.

## Questions
1. Why does decorrelation matter as much as increasing the number of trees?
2. How do we derive the 63.2% rule?
3. What are out-of-bag samples, and how can they estimate performance?
4. Why does bagging work better with deep trees than with shallow stumps?
5. Can adding more trees make a Random Forest overfit in the usual way?
6. What are the two sources of randomness in a Random Forest?
7. What happens to the variance formula when correlation is 0? What about when it is 1?
8. How are predictions combined for classification and regression?
9. What does `max_features` control?
10. How is boosting different from bagging?

## Short answer key
1. Strongly correlated trees make similar errors; correlation creates a variance floor that more trees cannot remove.
2. A row is omitted from `n` draws with probability `(1 − 1/n)^n`, which approaches `e⁻¹ ≈ 0.368`; therefore, about `1 − 0.368 = 0.632`, or 63.2%, are included at least once.
3. OOB rows were not used to train a particular tree. Combine predictions from trees that left a row out to estimate performance.
4. Deep trees are high-variance and low-bias, so bagging has variance to reduce. Bagging is not mainly a bias-reduction method.
5. The session says more trees do not overfit a forest in the usual way; they cost additional computation.
6. Bootstrap sampling of rows and random feature subsets at each split.
7. If correlation is 0, variance is `σ²/B`; if it is 1, variance remains `σ²`.
8. Classification uses majority vote or averaged probabilities; regression averages numerical predictions.
9. It controls how many features are considered at each split.
10. Bagging trains models independently; boosting builds models sequentially to improve on earlier mistakes.
