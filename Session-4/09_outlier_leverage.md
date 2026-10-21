# Outliers, Leverage, Influence, and Remedies

## Outlier

An outlier is unusual in the target/residual direction.

In a regression plot, it may sit far away from the fitted line
vertically.

Think:

> **far from the line vertically**

------------------------------------------------------------------------

## Leverage

A high-leverage point has an unusual input value.

It is far from the other observations in the feature space.

Think:

> **far away horizontally in X-space**

A leverage point does not automatically mean it is harmful.

------------------------------------------------------------------------

## Influence

An observation is influential if removing it causes the fitted
regression model to change noticeably.

Think:

> **Does this one row have the power to move my model?**

Influence often happens when a point has both:

-   high leverage
-   unusual target/residual behavior

------------------------------------------------------------------------

## Cook's distance

Cook's distance is a standard measure of influence.

It summarizes how much the fitted model changes when one observation is
removed.

Large Cook's distance values identify observations that deserve
investigation.

## Important warning

Do not automatically delete an outlier.

First ask:

-   Is it a data-entry error?
-   Is it a legitimate rare case?
-   Is it from a different population?
-   Is it revealing that the model is incomplete?

------------------------------------------------------------------------

# Remedies

## Non-linearity

Possible fixes:

-   polynomial features
-   log transformation
-   square-root transformation
-   another model that can represent the relationship

## Heteroscedasticity

Possible fixes:

-   transform the target, such as using log(y)
-   weighted least squares
-   consider models/standard errors appropriate for unequal variance

## Multicollinearity

Possible fixes:

-   remove redundant features
-   combine features
-   use Ridge regression

## Outliers

Possible approach:

1.  Investigate the observation.
2.  Correct data errors if present.
3.  Transform variables if appropriate.
4.  Consider robust modeling.
5.  Cap values only when scientifically justified.

## Non-normal residuals

If inference is required, investigate transformations or alternative
inference methods.

If the only goal is prediction and predictions are good, non-normal
residuals may be acceptable.

------------------------------------------------------------------------

## Connection to Ridge

The file points forward to Ridge regression.

The Ridge penalty adds a term involving:

\[ `\lambda `{=tex}I \]

This helps stabilize the matrix problem caused by strong collinearity.

So a useful mental connection is:

> **Multicollinearity → unstable OLS → Ridge can stabilize the
> coefficients.**
