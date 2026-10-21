# 01 — Underfitting and Overfitting

## 1. What is model fitting?

A machine-learning model tries to learn a relationship between inputs `X` and output `y`.

The important question is:

> Does the model learn the real pattern, or does it fail to learn it / memorize the training data?

There are three useful situations:

| Situation | Training error | Test error | Main idea |
|---|---:|---:|---|
| Underfitting | High | High | Model is too simple |
| Good fit | Low | Low | Model captures useful pattern |
| Overfitting | Very low | High | Model learns training noise too |

## 2. Underfitting

Underfitting means the model is **too simple** to capture the actual relationship.

Example:

Suppose the real relationship looks curved:

```text
y
|        *
|     *     *
|   *         *
|_*______________ x
```

If we use a straight line, the model may miss the curve.

### Simple analogy

A student memorizes one rule and applies it to every question. The student makes mistakes in a consistent way.

This is **high bias**.

### What can help?

The session says that high bias can be addressed with:

- a more expressive model
- better features

More training data generally does **not** solve a high-bias problem when the model itself is too limited.

## 3. Overfitting

Overfitting means the model becomes too sensitive to the particular training dataset.

It may fit the training observations extremely well, including random noise, but perform badly on new observations.

### Simple analogy

A student memorizes every previous exam paper exactly.

They may perform very well on questions they have already seen, but struggle with a new question.

This is **high variance**.

### Typical pattern

```text
Training error → very low
Test/validation error → high
```

A large persistent train-validation gap is a classic sign of high variance.

### What can help?

The session identifies these possible directions:

- simpler models
- more data
- regularization
- ensembling

## 4. The easiest memory trick

### High bias

> Model is **not paying enough attention to the data**.

Usually:

```text
Too simple → underfit → high bias
```

### High variance

> Model is paying **too much attention to noise** in the training data.

Usually:

```text
Too complex → overfit → high variance
```

## 5. Exam shortcut

If you see:

> Training error high + test error high

Think:

**Underfitting / high bias**

If you see:

> Training error very low + test error high

Think:

**Overfitting / high variance**
