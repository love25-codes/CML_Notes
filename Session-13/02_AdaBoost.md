# 2. AdaBoost

AdaBoost means **Adaptive Boosting**. It trains weak learners one at a time and changes the importance, or weight, of training examples after each round.

## How it works
1. Start by giving training examples equal weights.
2. Train a weak learner, often a tiny decision tree.
3. Measure its **weighted error** \(\epsilon_t\).
4. Give the learner a vote weight \(\alpha_t\).
5. Increase the weights of examples it classified incorrectly.
6. Normalize the example weights and train the next learner.
7. Combine learners using their weighted votes.

## Vote weight

\[
\alpha_t = \frac{1}{2}\ln\left(\frac{1-\epsilon_t}{\epsilon_t}\right)
\]

Here, \(\epsilon_t\) is the learner's weighted error. Lower error means a stronger vote.

| Weighted error | Vote weight (approx.) | Meaning |
|---:|---:|---|
| 0.01 | 2.3 | Strong vote |
| 0.40 | 0.20 | Small positive vote |
| 0.50 | 0 | No useful vote |
| 0.60 | -0.20 | Negative / inverted vote under this formula |

## Why reweight examples?
Incorrectly classified examples get more weight, so the next learner pays more attention to them. The weights are then normalized so they form a usable distribution.

## Weakness
The lecture notes that AdaBoost minimizes **exponential loss**. A mislabeled example or outlier can keep gaining importance, making AdaBoost sensitive to label noise and outliers.

**Remember:** AdaBoost adjusts both the importance of examples and the voting power of each learner.
