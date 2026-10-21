# Mathematical Foundation of the Assumptions

The file writes linear regression as:

\[ y = X`\beta `{=tex}+ `\varepsilon`{=tex} \]

## What do the symbols mean?

-   **y** = target/output values
-   **X** = matrix containing the input features
-   **β** = true model coefficients
-   **ε** = errors/noise

In simple words:

> observed target = systematic model part + random error

The file then assumes:

\[ E\[`\varepsilon`{=tex}\] = 0 \]

and

\[ Var(`\varepsilon`{=tex}) = `\sigma`{=tex}\^2 I \]

## What does E\[ε\] = 0 mean?

The errors have an average of zero.

The model is not systematically too high or systematically too low.

This supports unbiased coefficient estimates.

------------------------------------------------------------------------

## What does Var(ε) = σ²I mean?

This compact matrix statement contains two important ideas.

### σ²

The errors have a common variance.

That corresponds to **homoscedasticity**.

### I

The identity matrix has:

-   constant values on the diagonal
-   zeros off the diagonal

The zero off-diagonal entries represent **independence/no covariance
between errors**.

So:

\[ Var(`\varepsilon`{=tex})=`\sigma`{=tex}\^2I \]

can be understood as:

> equal error variance + independent errors.

------------------------------------------------------------------------

## Coefficient properties

Under the relevant assumptions, the file gives:

\[ E\[`\hat{\beta}`{=tex}\] = `\beta`{=tex} \]

This means the estimated coefficients are **unbiased**.

It also gives:

\[ Var(`\hat{\beta}`{=tex}) = `\sigma`{=tex}^2(X^TX)\^{-1} \]

This tells us how variable the estimated coefficients are.

## Why multicollinearity matters

If features are highly correlated, (X\^TX) becomes close to singular.

Its inverse can become very large.

That makes coefficient estimates unstable.

This is why multicollinearity can cause:

-   coefficients to swing
-   signs to flip
-   difficult interpretation
-   large coefficient uncertainty

Interestingly, **normality does not appear in these equations**, which
explains why normality is mainly needed for classical inference rather
than for the basic unbiasedness result.
