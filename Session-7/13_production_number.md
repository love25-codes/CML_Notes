# 13 — Is 0.92 My Production Number?

## The question

Suppose you run GridSearchCV and get:

$$
0.92
$$

Can you simply say:

> "My production model will get 0.92"?

The session asks us to question that assumption.

## Why?

GridSearchCV uses cross-validation folds to search for good hyperparameters.

Those validation folds were involved in the model-selection process.

Therefore, that score should not automatically be treated as a completely untouched final performance measurement.

## The key idea

We need a way to measure performance honestly after model selection.

The session connects this to:

> **Nested Cross-Validation**

Nested CV separates the process of:

1. Choosing/tuning the model.
2. Evaluating the model.

## Simple mental model

```text
Outer CV
└── honest evaluation

    Inner CV
    └── choose hyperparameters
```

The important lesson is:

> A score produced while tuning the model is not automatically the same thing as an untouched production-performance estimate.
