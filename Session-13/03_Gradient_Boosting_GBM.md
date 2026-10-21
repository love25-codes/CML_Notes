# 3. Gradient Boosting (GBM)

Gradient Boosting builds a strong model by repeatedly adding small models that improve the current predictions.

## Basic algorithm
1. Start with a simple constant prediction. For regression with squared error, this is the mean of the target values.
2. Calculate the residual for each row:

   \[
   r = y - \hat{y}
   \]

   - \(y\): actual value
   - \(\hat{y}\): current predicted value
   - \(r\): how far the prediction is from the truth
3. Train a small tree to predict those residuals.
4. Add part of the tree's prediction to the current prediction:

   \[
   \hat{y}_{new} = \hat{y}_{old} + \eta \times \text{tree prediction}
   \]

5. Recalculate residuals and repeat.

## What is the learning rate \(\eta\)?
The learning rate controls how much each new tree changes the current prediction. A smaller value makes smaller, more cautious updates.

## Simple example
Actual values are \(y = \{10,20,30\}\). Start by predicting the mean, 20, for every row.

- Initial predictions: \(\{20,20,20\}\)
- Residuals: \(\{-10,0,+10\}\)
- Suppose a tree predicts residuals \(\{-8,0,+8\}\).
- With learning rate \(\eta=0.5\), new predictions become:

  \[
  \{20,20,20\} + 0.5\{-8,0,8\} = \{16,20,24\}
  \]

- New residuals are \(\{-6,0,+6\}\).

The errors have become smaller. Another tree can try to improve them further.

**Remember:** Each new tree learns what the current model is still missing; it does not start from scratch.
