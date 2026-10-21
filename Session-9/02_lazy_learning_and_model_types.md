# 2. Lazy Learning and Model Types

## Why is KNN called a lazy learner?
KNN does very little work during training. It mainly stores the training examples. When a new prediction is requested, it calculates distances and finds the neighbours then.

That means the “work” is delayed until prediction time.

## What does “the model is the data” mean?
Many algorithms learn a smaller set of parameters that summarise patterns in the data. Basic KNN instead keeps the examples and refers back to them for each prediction.

## Parametric vs non-parametric
- **Parametric model:** assumes a particular model structure and learns a fixed set of parameters. The learned parameters summarise the data.
- **Non-parametric model:** does not require a fixed, small parameter count in the same way. Basic KNN retains the training examples, so its stored model grows with the dataset.

“Non-parametric” does **not** mean that the algorithm has no settings. KNN still has choices such as `k` and the distance metric.

## Advantages
- Simple to understand.
- Little or no explicit fitting process.
- Can model complicated local patterns.

## Disadvantages
- Stores the training data.
- Prediction can be slow on large datasets.
- Sensitive to feature scaling and irrelevant features.

## Main takeaway
KNN has a light training phase but does more work whenever it predicts.
