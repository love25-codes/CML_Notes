# 12 — Cross-Validation Must Run Inside a Pipeline

## The most important idea

When using preprocessing such as scaling, the preprocessing must happen **inside the cross-validation process**.

## The leakage problem

Suppose you scale the complete dataset first:

```text
Entire dataset
      ↓
Scale everything
      ↓
Cross-validation
```

The scaler has already seen the validation data.

That means information from the validation fold has leaked into the training process.

This is called:

> **Data leakage.**

## Correct approach

Put the scaler and model inside a **Pipeline**.

Conceptually:

```text
Fold
 ↓
Fit scaler only on training part
 ↓
Transform training part
 ↓
Transform validation part
 ↓
Train model
 ↓
Evaluate validation part
```

Then repeat for every fold.

Each fold gets its own fitted preprocessing step.

## Hyperparameter search

The session mentions two common tools.

### GridSearchCV

It searches through a specified grid of hyperparameter values.

Think:

> "Try all the combinations I gave you."

### RandomizedSearchCV

It samples combinations instead of trying every possible combination.

This can be useful when there are many hyperparameters, especially when many possible values are not very important.

## Nested CV

When hyperparameters are also being tuned using CV, **nested cross-validation** is described as the honest way to report performance.

## Main rule

> **Anything that learns from the data must be fitted inside the appropriate training fold.**

For preprocessing, the easiest practical rule is:

> **Put the preprocessing + model inside a Pipeline before CV.**
