# 12. Should You Use K = 1?

## The tempting idea
With `k = 1`, KNN gets 100% training accuracy in the standard setup because each training example is its own nearest neighbour.

It may seem that `k = 1` must therefore be the best choice.

## Why that conclusion is wrong
Training accuracy measures performance on examples the model already has. Test accuracy measures performance on separate, unseen examples.

With `k = 1`, the decision boundary can bend around individual training points and noise. That can make predictions unstable on new data.

This is called **overfitting**: the model fits the training set very closely but does not generalise as well as hoped.

## What should you do instead?
Evaluate multiple values of `k` using cross-validation, then check final performance on a held-out test set.

## Main takeaway
Perfect training accuracy does not guarantee good test accuracy. Do not choose `k = 1` based only on training performance.
