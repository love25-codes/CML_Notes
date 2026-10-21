# Session 8 --- Should I Be Pleased?

## The question

Suppose someone says:

> "My fraud model has 99% accuracy."

Do not immediately conclude that the model is useful.

First ask:

> **What is the base rate?**

------------------------------------------------------------------------

# What is the base rate?

The base rate is the proportion of cases belonging to a class.

For example:

``` text
99% legitimate
1% fraud
```

The fraud base rate is only 1%.

------------------------------------------------------------------------

# Compare against a simple baseline

Ask:

> What would happen if I always predicted legitimate?

If 99% of the data is legitimate, that simple strategy gets:

\[ 99% \]

accuracy.

Therefore, a model with 99% accuracy may not be doing anything useful
for fraud detection.

------------------------------------------------------------------------

# What should you inspect?

For an imbalanced fraud problem, look beyond accuracy.

Useful questions include:

-   How many fraud cases did we catch?
-   What is recall?
-   What is precision?
-   What is F1?
-   What is PR-AUC?
-   How does the model compare with a simple majority-class baseline?
-   What threshold is being used?
-   What are the costs of false positives and false negatives?

------------------------------------------------------------------------

# Main lesson

A metric has meaning only in context.

A high score does not automatically mean the model solves the actual
problem.

For fraud detection, the important question is not simply:

> "How many predictions were correct?"

It is also:

> "Did we actually detect the rare cases we care about?"

------------------------------------------------------------------------

## Memory trick

Whenever you see:

> **"99% accuracy!"**

immediately ask:

> **"What is the class distribution?"**
