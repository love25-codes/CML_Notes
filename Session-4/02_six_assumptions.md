# The Six Linear Regression Assumptions

## 1. Linearity

The model assumes that the relationship can be represented reasonably
well by a straight-line structure.

If the true relationship is strongly curved but we force a straight
line, predictions can become systematically wrong.

### Example

If study hours and marks follow a curve rather than a straight trend, a
simple linear model may miss the pattern.

### Diagnostic

Look at residuals. A **curve or U-shape** is a warning sign of
non-linearity.

------------------------------------------------------------------------

## 2. Independence

The error for one observation should not depend on the error of another
observation.

This is especially important for time-series data.

### Example

If today's prediction error is strongly related to yesterday's error,
the observations are not independent.

### Diagnostic

Look for a trend in residuals over the observation index/time.
Durbin--Watson is one commonly used diagnostic.

------------------------------------------------------------------------

## 3. Homoscedasticity

This means the residuals should have approximately the **same spread**
across fitted values.

### Good pattern

Residuals look like random noise with a similar vertical spread
everywhere.

### Bad pattern

A **funnel/cone shape**, where residuals become wider or narrower as
fitted values increase.

This is called **heteroscedasticity**.

------------------------------------------------------------------------

## 4. Normality of residuals

Residuals are assumed to be approximately normally distributed when we
want classical statistical inference.

This assumption is mainly about:

-   p-values
-   confidence intervals
-   hypothesis tests

It is **not automatically required for good point predictions**.

------------------------------------------------------------------------

## 5. Low multicollinearity

Input features should not be almost duplicates of each other.

### Example

Suppose we use:

-   house area in square feet
-   house area in square meters

These contain essentially the same information.

The model may struggle to decide how much coefficient weight belongs to
each feature.

------------------------------------------------------------------------

## 6. No highly influential observations

No single observation should have an unusually large effect on the
fitted regression line.

Three related ideas are:

-   **Outlier** --- unusual in the target/residual direction.
-   **Leverage** --- unusual in the input-feature space.
-   **Influence** --- removing the observation noticeably changes the
    fitted model.

Cook's distance is a common measure of influence.
