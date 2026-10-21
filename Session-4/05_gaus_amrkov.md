# Gauss--Markov Theorem and BLUE

## What is Gauss--Markov?

The file introduces the **Gauss--Markov theorem**.

Its main message is:

> Under the appropriate linear regression assumptions, ordinary least
> squares (OLS) is BLUE.

## BLUE means

**B**est\
**L**inear\
**U**nbiased\
**E**stimator

### Best

Among linear unbiased estimators, OLS has the **minimum variance**.

### Linear

The estimator is linear in the observed target values.

### Unbiased

On average:

\[ E\[`\hat{\beta}`{=tex}\] = `\beta`{=tex} \]

So the estimator does not systematically overestimate or underestimate
the true coefficient.

## Important surprise

**Normality of the errors is not required for Gauss--Markov.**

You do not need the residuals to follow a perfect bell curve for OLS to
be BLUE.

Normality becomes important mainly when doing classical statistical
inference such as:

-   confidence intervals
-   hypothesis tests
-   p-values

## Easy way to remember

Think:

> **Gauss--Markov gives OLS its BLUE property without requiring a bell
> curve.**
