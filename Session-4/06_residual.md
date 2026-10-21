# Residual Diagnostics

## What is a residual?

A residual is the difference between the actual target and the model's
prediction:

\[ e_i = y_i - `\hat{y}`{=tex}\_i \]

Where:

-   (y_i) = actual value
-   (`\hat{y}`{=tex}\_i) = predicted value
-   (e_i) = residual/error for observation i

## Why do we inspect residuals?

A regression line can look good while hiding important problems.

Residuals help us see whether the model has missed a pattern.

A healthy residual plot should look approximately like:

> random dots scattered around zero.

There should not be a clear structure.

## Common patterns

### 1. Curve / U-shape

**Diagnosis:** non-linearity.

The model is missing a curved relationship.

### 2. Funnel / cone

**Diagnosis:** heteroscedasticity.

The error variance changes as fitted values change.

### 3. Clusters

**Possible diagnosis:** a missing variable or an unmodeled group
structure.

### 4. Trend over index/time

**Diagnosis:** autocorrelation/dependence.

The errors are not independent.

## Good residual plot

Random-looking scatter around zero.

## Bad residual plot

A visible pattern means:

> the model may still contain information that it has not captured.

## Practical workflow

1.  Fit the regression model.
2.  Calculate residuals.
3.  Plot residuals against fitted values.
4.  Look for curves, funnels, clusters, or trends.
5.  Investigate the cause.
6.  Apply an appropriate remedy if needed.
