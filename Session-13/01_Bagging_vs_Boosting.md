# 1. Bagging vs. Boosting

## What is an ensemble?
An ensemble combines several machine-learning models to make one stronger prediction.

## Bagging
Bagging means **Bootstrap Aggregating**. Multiple models are trained independently, often on different random samples of the training data. Their predictions are combined.

- Models can train in parallel.
- It mainly helps reduce **variance** (predictions that change too much with the training data).
- Random Forest is a common example.
- It often uses deeper decision trees, which can learn complex patterns but may vary a lot.

## Boosting
Boosting trains models **one after another**. Each new model focuses on what the current combined model is still getting wrong.

- Training is sequential because each round depends on the previous round.
- It often uses small, shallow trees called **stumps**.
- It mainly helps reduce **bias** (a model being too simple to learn the pattern).
- Too many trees can overfit the training data.

## Quick comparison

| Point | Bagging | Boosting |
|---|---|---|
| Training | Parallel / independent | Sequential |
| Main goal | Reduce variance | Reduce bias |
| Common base trees | Deeper trees | Shallow trees |
| More trees | Often relatively safe, but not a universal guarantee | Can eventually overfit |
| Example | Random Forest | AdaBoost, Gradient Boosting, XGBoost |

**Memory trick:** Bagging builds models separately and averages them; boosting builds models in a sequence to correct remaining errors.
