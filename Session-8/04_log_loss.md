# Session 8 --- Log-Loss, One Row at a Time

## What is log-loss?

Log-loss is the loss function used for logistic regression
classification.

It is also called **cross-entropy loss**.

The formula is:

\[ J(`\beta`{=tex}) = -`\frac{1}{n}`{=tex} `\sum`{=tex}\_{i=1}\^{n}
`\left[
y_i\log(\hat p_i)
+
(1-y_i)\log(1-\hat p_i)
\right]`{=tex}\]

You do not need to be scared by the formula. It becomes very simple when
we look at one row.

------------------------------------------------------------------------

## Case 1: Actual class is 1

If:

\[ y=1 \]

then:

\[ 1-y=0 \]

So the loss becomes:

\[ -`\log`{=tex}(`\hat `{=tex}p) \]

### Good prediction

Suppose:

\[ `\hat `{=tex}p=0.99 \]

Then:

\[ -`\log`{=tex}(0.99)`\approx0.01`{=tex} \]

Very small loss.

### Bad prediction

Suppose:

\[ `\hat `{=tex}p=0.01 \]

Then:

\[ -`\log`{=tex}(0.01)`\approx4.6`{=tex} \]

Large loss.

So if the true class is 1:

``` text
predict near 1 → small loss
predict near 0 → huge loss
```

------------------------------------------------------------------------

## Case 2: Actual class is 0

Now:

\[ y=0 \]

The loss becomes:

\[ -`\log`{=tex}(1-`\hat `{=tex}p) \]

### Good prediction

If:

\[ `\hat `{=tex}p=0.01 \]

then the model correctly gives a low probability to class 1.

Loss is very small.

### Bad prediction

If:

\[ `\hat `{=tex}p=0.99 \]

the model is extremely confident that the answer is 1 even though the
truth is 0.

The loss becomes very large.

------------------------------------------------------------------------

## Why punish confident mistakes?

Imagine two models:

``` text
Model A: "I think it is 60% class 1."
Model B: "I am 99.9% sure it is class 1."
```

If the true answer is 0, Model B should be punished much more heavily
because it was **very confident and very wrong**.

That is exactly what log-loss does.

------------------------------------------------------------------------

## Why not MSE?

The session's main idea is that logistic regression is built around
probabilities and the Bernoulli likelihood.

Log-loss is the natural loss coming from **Bernoulli maximum likelihood
estimation**.

It also gives the useful behavior of strongly penalizing confident wrong
predictions.

------------------------------------------------------------------------

## Memory trick

> **Log-loss hates confident wrong answers.**

Remember:

``` text
Correct + confident → tiny loss
Wrong + uncertain  → moderate loss
Wrong + confident  → huge loss
```
