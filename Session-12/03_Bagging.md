# 3. Bagging (Bootstrap Aggregating)

## What is bagging?
**Bagging** is short for **Bootstrap Aggregating**. It is a method for combining predictions from multiple models.

## How it works
1. Create several training datasets by sampling rows from the original dataset **with replacement**.
2. Train a separate model on each sample.
3. Combine the models' predictions.

Because sampling is done with replacement, a row can appear more than once in one sample, while another row may be left out.

## How predictions are combined
- **Classification:** use the majority vote, or average the predicted probabilities.
- **Regression:** average the numerical predictions.

## Why use deep trees?
The session recommends bagging deep, unpruned decision trees. Deep trees can have low bias but high variance, so bagging targets a problem they actually have: instability.

Bagging shallow decision stumps is described as much less useful because bagging mainly reduces variance rather than bias.

## Key takeaway
Bagging trains models independently and combines their outputs to reduce variance. It is a general technique, but it works particularly well with high-variance decision trees.
