# Linear Regression --- Assumptions

## Big idea

A linear regression model can have a very good-looking fit and still be
misleading. The file uses **Anscombe's Quartet** to show that datasets
can have almost identical summary statistics and regression lines while
having completely different patterns.

So, a high **R²** does not automatically mean the model is valid.

The purpose of regression assumptions is to check whether the model is
trustworthy.

## The six assumptions/checks

1.  **Linearity** --- the relationship between inputs and target is
    approximately linear.
2.  **Independence** --- errors/residuals are independent.
3.  **Homoscedasticity** --- residuals have roughly constant variance.
4.  **Normality of residuals** --- residuals are approximately normal,
    mainly important for statistical inference.
5.  **Low multicollinearity** --- input features should not be almost
    duplicates of each other.
6.  **No highly influential observations** --- one or a few rows should
    not control the fitted model.

## Most important distinction

Ask:

> Am I mainly interested in **predictions**, or in **inference** such as
> p-values and confidence intervals?

Some assumption violations mainly damage inference, while others can
damage predictions too.

## Mental model

Think of the assumptions as a **health check for linear regression**:

**Fit model → inspect residuals → check independence → check normality →
check multicollinearity → check influential points → decide what to
fix.**
