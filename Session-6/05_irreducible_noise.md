# 05 — Irreducible Noise, Variance and Bias

## 1. Irreducible noise

### Meaning

Irreducible noise is randomness in the target that exists even when the input is known.

The session describes it as:

> inherent randomness of `y` given `x`

### Can we reduce it?

Not by simply changing the model.

It is the model's unavoidable error floor.

### Example

Suppose two people with exactly the same measurable features can still have slightly different outcomes because of randomness that is not captured in the available features.

That unpredictable part contributes to noise.

---

## 2. Variance

### Meaning

Variance asks:

> How much does my model's prediction change when I train it on a different dataset?

High variance means the fitted model is highly dependent on the particular sample.

### High variance behavior

Imagine training five models:

```text
Dataset 1 → prediction = 20
Dataset 2 → prediction = 35
Dataset 3 → prediction = 10
Dataset 4 → prediction = 40
Dataset 5 → prediction = 15
```

The predictions move around a lot.

That means high variance.

### Ways to reduce variance

The session mentions:

- simpler models
- more data
- ensembling

Regularization is also introduced as a way of restricting the class of functions we fit.

---

## 3. Bias squared

### Meaning

Bias squared measures how far the average model prediction is from the true/best possible prediction.

If a model is too simple, it may consistently miss the real relationship.

That gives high bias².

### Example

Suppose the true relationship is strongly curved, but your model is only capable of fitting a straight line.

The model may consistently be wrong in a similar direction.

That is high bias.

### Ways to reduce bias

The session mentions:

- more expressive models
- better features

---

## 4. Comparison

| Term | Simple meaning | Usually high when |
|---|---|---|
| Noise | Randomness you cannot simply remove | Data itself is noisy |
| Bias² | Average prediction is far from truth | Model is too simple |
| Variance | Prediction changes a lot across datasets | Model is too sensitive/complex |

## 5. Two useful thought experiments

### Question A

If a model fits the training data perfectly every time, what happens to variance?

The session's answer:

> Variance is maximal — the model chases noise and changes completely with every sample.

The important lesson is that a model can have extremely low training error while still being unstable.

### Question B

If the model is a flat line every time, what happens?

The session's answer:

> Variance approaches zero, but bias² becomes large.

Why?

Because the model barely changes between datasets, but it ignores the actual signal.

## 6. Memory trick

```text
Bias = consistently wrong
Variance = inconsistently wrong
Noise = impossible-to-remove randomness
```
