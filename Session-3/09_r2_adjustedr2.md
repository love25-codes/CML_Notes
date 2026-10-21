# 9. R² and Adjusted R²

## R²

The coefficient of determination is:

```text
R² = 1 - RSS/TSS
```

where:

```text
RSS = Σ(yᵢ - ŷᵢ)²
```

is residual sum of squares, and:

```text
TSS = Σ(yᵢ - ȳ)²
```

is total sum of squares.

## Intuition

R² measures how much of the variation in the target is explained by the model.

For example:

```text
R² = 0.90
```

means the model explains 90% of the variation in the target (under the usual interpretation).

## The trap

Plain R² never decreases when you add another feature to a linear regression model.

Even if the new feature is just random noise, R² can increase.

Therefore, a higher R² does not automatically mean the new model is better.

## Adjusted R²

Adjusted R² accounts for the number of predictors:

```text
Adjusted R² =
1 - [(1 - R²)(n - 1)] / [n - p - 1]
```

Because it penalizes unnecessary features, adjusted R² can decrease when a feature does not provide enough useful information.

## Simple rule

- R² → rewards added predictors
- Adjusted R² → asks whether the added predictors are worth the extra complexity

## Big ML lesson
A model should be judged by both **fit** and **complexity**, not fit alone.
