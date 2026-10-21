# Q--Q Plot and Durbin--Watson

## Q--Q plot

A Q--Q plot compares:

> observed residual quantiles vs theoretical normal quantiles.

### How to read it

If points are approximately on a straight diagonal line:

> residuals are reasonably close to normal.

### Common patterns

-   **Approximately straight line** → normality looks reasonable.
-   **S-shape** → possible heavy tails.
-   **Bending at the ends** → possible skewness/tail problems.

The important point is to read the plot visually rather than relying on
one number.

------------------------------------------------------------------------

## Durbin--Watson

Durbin--Watson is used to detect autocorrelation in residuals.

A simple interpretation:

-   **Around 2** → little/no first-order autocorrelation.
-   **Near 0** → strong positive autocorrelation.

Positive autocorrelation often appears when a time-based pattern has not
been modeled.

## Example

Imagine predicting daily sales.

If today's residual is positive and tomorrow's residual is also usually
positive, the errors may be related over time.

That violates independence.

## Remember

-   **Q--Q plot → mainly normality**
-   **Durbin--Watson → independence/autocorrelation**
