# 6. The 1-NN Error Guarantee

The lecture presents this theoretical result:

\[
\text{error}_{1\text{-NN}} \leq 2 \times \text{Bayes error}
\]

## What is Bayes error?
Bayes error is the lowest possible classification error for the given problem when using the true underlying probabilities. It represents error that cannot be avoided because the classes may overlap or the data may be inherently uncertain.

## What is 1-NN?
`1-NN` means KNN with `k = 1`: copy the label of the closest training example.

## What does the guarantee mean?
Under the assumptions of the relevant theoretical result, the asymptotic error of 1-NN is bounded by twice the Bayes error. In simple words, the nearest-neighbour rule can be surprisingly competitive compared with the best possible classifier.

## Important caution
This is a theoretical result, not a promise that 1-NN will perform well on every small dataset or every real-world problem. Noise, finite data, poor scaling, and irrelevant features can still hurt it.

## Main takeaway
Although 1-NN is simple, theory gives a reason to take it seriously as a baseline.
