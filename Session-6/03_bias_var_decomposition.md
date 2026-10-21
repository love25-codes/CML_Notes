# 03 — Bias–Variance Decomposition

## 1. The main equation

The session gives the decomposition:

\[
E_{y,S}[(y-f_S(x))^2]
=
\underbrace{E_y[(y-\bar y)^2]}_{\text{irreducible noise}}
+
\underbrace{E_S[(\bar f(x)-f_S(x))^2]}_{\text{variance}}
+
\underbrace{(\bar y-\bar f(x))^2}_{\text{bias}^2}
\]

In simple words:

```text
Expected prediction error
= irreducible noise
+ variance
+ bias²
```

This is the main equation to remember.

## 2. What do the symbols mean?

### `f_S(x)`

`S` represents a particular training set.

If we train our model using that particular dataset, we get a model called:

```text
f_S
```

Because a different training sample can produce a different fitted model, `f_S` is treated as a random object.

### `\bar f(x)`

This is the average prediction of the model over many possible training sets:

\[
\bar f(x)=E_S[f_S(x)]
\]

Think:

> "If I trained the same type of model on many different datasets, what prediction would I get on average?"

### `\bar y`

This is:

\[
\bar y=E[y|x]
\]

The session describes it as the best possible predictor.

## 3. Irreducible noise

\[
E_y[(y-\bar y)^2]
\]

This represents randomness in `y` that remains even when `x` is known.

The session calls it:

> inherent randomness of `y` given `x`

It cannot be removed simply by choosing a different model.

Therefore:

```text
Irreducible noise = error floor
```

## 4. Variance

\[
E_S[(\bar f(x)-f_S(x))^2]
\]

This asks:

> How much does the prediction change when the training dataset changes?

If small changes in the training sample produce very different models, variance is high.

## 5. Bias squared

\[
(\bar y-\bar f(x))^2
\]

This asks:

> How far is the average model prediction from the true/best possible prediction?

A model that is too simple can have large bias.

## 6. Why is it useful?

Instead of saying only:

> "The model has high error."

we can ask:

> "Which component is causing the error?"

Then we can choose a direction:

| Problem | Possible direction |
|---|---|
| High bias | More expressive model / better features |
| High variance | Simpler model / more data / ensembling / regularization |
| Irreducible noise | Cannot simply remove it |

## 7. One-line memory rule

```text
ERROR = BIAS² + VARIANCE + NOISE
```

The session emphasizes that this equation organizes the rest of the topic.
