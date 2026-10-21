# Linear Regression Assumptions --- Revision Checklist

## Must know

### Six checks

-   [ ] Linearity
-   [ ] Independence
-   [ ] Homoscedasticity
-   [ ] Normality of residuals
-   [ ] Low multicollinearity
-   [ ] No highly influential points

## Residual patterns

  Pattern                 Think
  ----------------------- ----------------------------------
  Curve / U-shape         Non-linearity
  Funnel                  Heteroscedasticity
  Clusters                Missing variable/group structure
  Trend over time/index   Autocorrelation

## Important formulas

### Residual

\[ e_i = y_i-`\hat{y}`{=tex}\_i \]

### Linear regression model

\[ y=X`\beta`{=tex}+`\varepsilon`{=tex} \]

### Error assumptions

\[ E\[`\varepsilon`{=tex}\]=0 \]

\[ Var(`\varepsilon`{=tex})=`\sigma`{=tex}\^2I \]

### Unbiased estimator

\[ E\[`\hat{\beta}`{=tex}\]=`\beta`{=tex} \]

### Coefficient variance

\[ Var(`\hat{\beta}`{=tex})=`\sigma`{=tex}^2(X^TX)\^{-1} \]

### VIF

\[ VIF_j=`\frac{1}{1-R_j^2}`{=tex} \]

## Diagnostics

-   Residual plot → linearity + variance patterns
-   Q--Q plot → residual normality
-   Durbin--Watson → autocorrelation/independence
-   VIF → multicollinearity
-   Cook's distance → influence

## High-value interview questions

### 1. Does non-normality always hurt prediction?

No. It mainly threatens classical inference such as p-values and
confidence intervals.

### 2. What does VIF = 10 mean?

It corresponds to (R_j\^2=0.9), meaning feature j can be strongly
explained by the other features.

### 3. What does Gauss--Markov say?

OLS is BLUE: the best linear unbiased estimator, under the relevant
assumptions.

Normality is not required for this result.

### 4. Outlier vs leverage vs influence?

-   Outlier → unusual in y/residual direction.
-   Leverage → unusual in X/features.
-   Influence → removing it changes the fitted model substantially.

### 5. Funnel-shaped residual plot?

Diagnosis: heteroscedasticity.

Possible fixes include transforming the target or using weighted least
squares.

## Final mental model

**Fit → Residuals → Independence → Normality → VIF → Influence → Fix →
Refit → Validate**

The most important habit is to separate:

> **prediction quality** from **inference quality**.
