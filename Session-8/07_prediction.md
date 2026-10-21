# Session 8 --- A Prediction, Then the Metrics

This section walks through a complete example.

------------------------------------------------------------------------

# Part A --- Turn a score into a probability

The model is:

\[ z=-4+2x \]

Suppose:

\[ x=3 \]

Then:

\[ z=-4+2(3)=2 \]

Now apply the sigmoid:

\[ `\sigma`{=tex}(2) = `\frac{1}{1+e^{-2}}`{=tex} \]

Since:

\[ e\^{-2}`\approx0.135`{=tex} \]

we get:

\[ `\sigma`{=tex}(2) `\approx`{=tex} `\frac{1}{1+0.135}`{=tex}
`\approx0.88`{=tex} \]

So the predicted probability of class 1 is approximately:

\[ 88% \]

If the threshold is 0.5:

\[ 0.88\>0.5 \]

Therefore:

``` text
Prediction = class 1
```

------------------------------------------------------------------------

# Part B --- Confusion matrix example

Suppose there are 100 emails.

                  Actual 1   Actual 0
  ------------- ---------- ----------
  Predicted 1      TP = 40    FP = 10
  Predicted 0      FN = 20    TN = 30

So:

``` text
TP = 40
FP = 10
FN = 20
TN = 30
```

------------------------------------------------------------------------

# Part C --- Calculate metrics

## Precision

\[ Precision = `\frac{40}{40+10}`{=tex} = 0.80 \]

So precision is:

\[ 80% \]

Meaning:

> Of the emails we flagged as positive, 80% were actually positive.

------------------------------------------------------------------------

## Recall

\[ Recall = `\frac{40}{40+20}`{=tex} `\approx0.67`{=tex} \]

So recall is approximately:

\[ 67% \]

Meaning:

> We found about 67% of all the actual positive cases.

------------------------------------------------------------------------

## F1

\[ F_1 = 2`\frac{0.80\times0.67}{0.80+0.67}`{=tex} `\approx0.73`{=tex}
\]

So:

\[ F_1`\approx73`{=tex}% \]

------------------------------------------------------------------------

## Accuracy

Correct predictions are:

\[ TP+TN=40+30=70 \]

Therefore:

\[ Accuracy=`\frac{70}{100}`{=tex}=70% \]

------------------------------------------------------------------------

## What does this example teach?

A model can have several different stories at the same time:

``` text
Accuracy = 70%
Precision = 80%
Recall ≈ 67%
F1 ≈ 73%
```

So one metric does not describe everything.

------------------------------------------------------------------------

## Memory trick

For every confusion-matrix question, first write:

``` text
TP
TN
FP
FN
```

Then choose the formula.

Do not try to calculate the metric from memory without identifying the
four values first.
