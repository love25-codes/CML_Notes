# Session 8 --- Odds and Log-Odds

## Why do we need odds?

Logistic regression works with probabilities, but its linear equation is
easier to understand through **odds** and **log-odds**.

If the probability of class 1 is `p`, then:

\[ `\text{odds}`{=tex}=`\frac{p}{1-p}`{=tex} \]

------------------------------------------------------------------------

## Probability vs odds

Suppose:

\[ p=0.8 \]

Then:

\[ 1-p=0.2 \]

So:

\[ `\text{odds}`{=tex}=`\frac{0.8}{0.2}`{=tex}=4 \]

This means the odds are **4 to 1** in favor of class 1.

------------------------------------------------------------------------

## What are log-odds?

Take the natural logarithm of the odds:

\[ `\log`{=tex}`\left`{=tex}(`\frac{p}{1-p}`{=tex}`\right`{=tex}) \]

Logistic regression assumes that this quantity is linear:

\[ `\log`{=tex}`\left`{=tex}(`\frac{p}{1-p}`{=tex}`\right`{=tex}) =
`\beta`{=tex}\_0+`\beta`{=tex}\_1x_1+`\beta`{=tex}\_2x_2+`\cdots`{=tex}
\]

This is called the **logit**.

------------------------------------------------------------------------

## Why is logistic regression called regression?

Because the model is linear in the **log-odds**.

It predicts:

``` text
features
   ↓
linear combination
   ↓
log-odds
   ↓
probability
```

So the "regression" part is the linear relationship.

------------------------------------------------------------------------

## Odds ratio

For coefficient (`\beta`{=tex}\_j):

\[ e\^{`\beta`{=tex}\_j} \]

is the **odds ratio**.

It tells us the multiplicative change in odds for a one-unit increase in
(x_j), holding the other variables fixed.

Example:

If:

\[ `\beta`{=tex}\_j=0.693 \]

then:

\[ e\^{0.693}`\approx2`{=tex} \]

So a one-unit increase in that feature multiplies the odds by
approximately **2**.

------------------------------------------------------------------------

## Very important distinction

Do not confuse:

-   probability
-   odds
-   odds ratio

Example:

``` text
Probability = 0.8

Odds = 0.8 / 0.2 = 4

Odds ratio = e^(coefficient)
```

------------------------------------------------------------------------

## Memory trick

Remember:

> **Probability → Odds → Log-Odds → Linear Model**

And:

> **Exponent of coefficient = odds ratio**
