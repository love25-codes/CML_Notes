# 09 — Validation Curves and Model Diagnosis

## 1. Learning curve vs validation curve

These are related but not the same.

### Learning curve

Plots model error against:

```text
Training-set size
```

It helps answer:

> Would more data help?

### Validation curve

Plots model error against a:

```text
Hyperparameter
```

The session specifically says:

> Validation curves instead plot error vs. a hyperparameter.

Examples of hyperparameters can include model complexity settings such as polynomial degree or regularization strength.

## 2. Training vs validation performance

Suppose someone says:

> "My model scores 99% on training and 70% on test."

The first thing to notice is:

```text
Training performance = very high
Test performance = much lower
```

That is a large generalization gap.

The session asks you to diagnose which decomposition term is large and what can shrink it.

The intended diagnosis is **high variance**.

## 3. Why?

A high training score means the model has fitted the training data very well.

A much lower test score means that performance does not transfer well to unseen data.

This is consistent with an overfitting/high-variance situation.

## 4. What are two different fixes?

The session gives the following directions for high variance:

### Fix 1 — More data

More representative training data can reduce variance.

### Fix 2 — Simplify or regularize

Reduce the model's ability to chase individual training observations.

Examples of the general idea include:

- simpler model
- lower polynomial degree
- regularization

The session also mentions ensembling as a way to reduce variance.

## 5. A useful decision process

When you see a model-performance question, ask:

### Step 1

Is training error high?

If yes, suspect high bias/underfitting.

### Step 2

Is training error very low but validation/test error high?

If yes, suspect high variance/overfitting.

### Step 3

For high bias:

Think:

```text
More expressive model
Better features
```

### Step 4

For high variance:

Think:

```text
More data
Simpler model
Regularization
Ensembling
```

## 6. Memory table

| Observation | Think |
|---|---|
| Train error high + test error high | High bias |
| Train error very low + test error high | High variance |
| Large persistent train-validation gap | High variance |
| Both curves converge to high error | High bias |
| More data not expected to help | High bias |
| More data can help | High variance |
