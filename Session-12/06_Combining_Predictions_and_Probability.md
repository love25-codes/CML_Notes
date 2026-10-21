# 6. Combining Predictions: Classification, Regression, and Probability

## Classification: voting
Each tree predicts a class. The forest can choose the class receiving the most votes.

### Example from the session
Five trees predict whether a patient is sick:

| Tree | Prediction |
|---|---|
| 1 | Sick |
| 2 | Sick |
| 3 | Well |
| 4 | Sick |
| 5 | Well |

There are three “Sick” votes and two “Well” votes, so the forest predicts **Sick**.

## Probability estimate
In this example, 3 out of 5 trees predict “Sick”:

\[
P(\\text{Sick})=\\frac{3}{5}=0.60
\]

That gives a simple forest-level estimate of 0.60, whereas an individual hard-label tree might output only one class label. The session also notes that averaging predicted probabilities is often preferable to only taking a majority vote.

## Regression: averaging numbers
For regression, each tree predicts a number. The forest averages those numerical predictions.

Example: predictions of 10, 12, and 14 produce an average of 12.

## Remember
- Classification → majority vote or average class probabilities.
- Regression → average numerical predictions.
