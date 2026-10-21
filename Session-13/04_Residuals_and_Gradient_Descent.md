# 4. Residuals as Negative Gradients

The key idea in gradient boosting is that, for squared-error loss, the residual is the **negative gradient** of the loss with respect to the prediction.

## Start with squared-error loss
For one example:

\[
L = \frac{1}{2}(y-\hat{y})^2
\]

Differentiate with respect to the prediction \(\hat{y}\):

\[
\frac{\partial L}{\partial \hat{y}} = \hat{y}-y
\]

So the negative gradient is:

\[
-\frac{\partial L}{\partial \hat{y}} = y-\hat{y}
\]

That is exactly the residual.

## Why does this matter?
Gradient descent normally updates model parameters in the direction that reduces loss. Gradient boosting uses a similar idea, but it adds a new function (a tree) to the model.

\[
F_m(x)=F_{m-1}(x)+\eta h_m(x)
\]

- \(F_{m-1}(x)\): current model
- \(h_m(x)\): new tree
- \(\eta\): learning rate
- \(F_m(x)\): updated model

For squared-error regression, fitting a tree to residuals approximates a step in the direction that reduces the loss.

## Classification
For classification, the model can use a different differentiable loss, such as log loss. The targets for the next tree are then based on the negative gradients of that loss, rather than simply the raw residuals.

**Memory trick:** Ordinary gradient descent adjusts parameters; gradient boosting adds small functions to improve predictions.
