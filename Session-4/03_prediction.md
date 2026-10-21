# Prediction vs Inference

One of the most important lessons in the file is that **not every
assumption violation affects predictions in the same way**.

## Prediction

Prediction asks:

> Can my model accurately predict new values?

For example:

> Given house size and location, what will the selling price be?

## Inference

Inference asks questions such as:

-   Is this feature statistically significant?
-   What is the confidence interval for a coefficient?
-   What is the p-value?
-   What can we conclude about the population?

## What happens when assumptions fail?

  -----------------------------------------------------------------------
  Problem                 Main consequence        Predictions
  ----------------------- ----------------------- -----------------------
  Non-linearity           Systematic bias         Can be bad

  Dependence              Standard errors can be  Often still usable
                          wrong                   

  Heteroscedasticity      Unequal uncertainty     Often usable, but some
                                                  ranges may be
                                                  unreliable

  Non-normal residuals    p-values/CIs may be     Usually can still be
                          invalid                 usable

  Multicollinearity       Coefficients become     Predictions may still
                          unstable                be fine

  Influential points      A few rows can change   Can be bad
                          the fit                 
  -----------------------------------------------------------------------

## Key exam/interview point

**Non-normal residuals do not automatically mean bad predictions.**

If you only need accurate point predictions, mild non-normality may not
be a major problem.

If you need confidence intervals or hypothesis tests, then residual
normality matters much more.

## Example

Suppose:

-   R² = 0.93
-   predictions are accurate
-   residual plot has a funnel shape

The model may still predict well.

But the funnel indicates **heteroscedasticity**, so uncertainty is not
constant. If you are reporting confidence intervals or standard errors,
the violation becomes more important.

Always ask what the model is being used for.
