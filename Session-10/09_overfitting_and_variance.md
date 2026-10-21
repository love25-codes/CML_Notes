# 9. Why Decision Trees Overfit

## What is overfitting?
Overfitting happens when a model learns the training examples too closely, including details that do not generalise to new data.

An unconstrained decision tree can keep splitting until it creates a leaf for nearly every training row. It may then achieve 100% training accuracy by memorising the training set rather than learning a pattern that works well on unseen examples.

## Training accuracy vs test accuracy
- **Training accuracy:** performance on examples used to train the model.
- **Test accuracy:** performance on separate examples the model did not train on.

If training accuracy is extremely high but test accuracy is much lower, that is a warning sign of overfitting.

## What is variance here?
A deep tree can be sensitive to small changes in its training data. Removing just a few rows may change the best split near the root, which can reshape the rest of the tree. This sensitivity is called **high variance**.

The session describes an unconstrained tree as having low bias but very high variance.

## What can help?
Limit the tree's growth—for example, by setting a maximum depth or using other stopping limits. The session points toward later material on methods that reduce the instability of a single tree.

## Remember
**A deep tree may fit training data extremely well but generalise poorly.** Perfect training accuracy is not automatically proof of a good model.
