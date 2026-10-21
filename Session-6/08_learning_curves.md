# 08 — Learning Curves

## 1. What is a learning curve?

A learning curve studies model performance as the **training-set size changes**.

The x-axis is usually:

```text
Training set size
```

and the y-axis is:

```text
Error
```

You normally compare training and validation/test error.

## 2. Why are learning curves useful?

They help diagnose whether the main problem is:

- high bias
- high variance

This makes them a practical diagnostic tool.

---

## 3. High-bias learning curve

The session describes high bias as a situation where:

> Both curves converge to a high error.

Conceptually:

```text
Error
 ^
 |  train  ─────────
 |  validation ──────
 |
 +--------------------> Training size
```

Both remain relatively high and close together.

### Interpretation

The model is too limited.

### Does more data solve it?

The session says:

> More data won't help; get a better model.

Possible direction:

- use a more expressive model
- improve features

---

## 4. High-variance learning curve

A high-variance model has a large, persistent gap between training and validation error.

Conceptually:

```text
Error
 ^
 | validation ─────────
 |
 | 
 | training  ─────
 |
 +--------------------> Training size
```

The exact curve shapes can vary, but the important clue is the persistent gap.

### Interpretation

The model fits training data much better than unseen data.

### Does more data help?

The session says:

> More data will help; or simplify / regularize.

Possible directions:

- collect more training data
- simplify the model
- use regularization

---

## 5. The key comparison

| Learning-curve pattern | Diagnosis | Typical action |
|---|---|---|
| Train and validation both high and close | High bias | More expressive model / better features |
| Large persistent train-validation gap | High variance | More data / simplify / regularize |

## 6. Easy memory trick

### High bias

```text
Both bad
```

### High variance

```text
Training good, validation bad
```

This is one of the most useful shortcuts for multiple-choice questions.

## 7. Important limitation

A learning curve is a diagnostic tool, not a magical answer.

The exact shape and context matter. But for the patterns presented in this session, the rules above are the intended interpretation.
