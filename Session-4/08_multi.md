# Multicollinearity and VIF

## What is multicollinearity?

Multicollinearity occurs when two or more input features contain very
similar information.

### Example

Suppose:

-   X₁ = income in rupees
-   X₂ = income in thousands of rupees

They are almost duplicates.

The model has difficulty separating their individual effects.

## Why is it a problem?

The overall model can still predict well, but individual coefficients
may become unstable.

You may see:

-   coefficients changing dramatically
-   coefficient signs flipping
-   large standard errors
-   difficult interpretation

So multicollinearity often hurts **interpretation** more than
prediction.

------------------------------------------------------------------------

## VIF

The file gives:

\[ VIF_j = `\frac{1}{1-R_j^2}`{=tex} \]

Here, (R_j\^2) is obtained by:

> regressing feature (j) on all the other features.

So VIF measures how much the information overlap among features inflates
the uncertainty of a coefficient.

## Examples

If:

\[ R_j\^2 = 0 \]

then:

\[ VIF = 1 \]

No linear relationship with the other features.

If:

\[ R_j\^2 = 0.9 \]

then:

\[ VIF = `\frac{1}{1-0.9}`{=tex}=10 \]

If (R_j\^2) approaches 1, VIF approaches infinity.

## Rule of thumb

-   **VIF ≈ 1** → little concern
-   **VIF \> 5** → warning
-   **VIF \> 10** → serious problem

These are rules of thumb, not universal laws.

## Practical fixes

-   Remove redundant features.
-   Combine related features.
-   Use dimensionality reduction when appropriate.
-   Use regularization such as **Ridge regression**.

## Deep intuition

The more the features share the same information, the harder it becomes
for OLS to decide which feature deserves which coefficient.

That is why the coefficient can become unstable even when the overall
predictions remain good.
