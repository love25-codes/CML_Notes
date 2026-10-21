# 11 — Cross-Validation Variants

Different kinds of data need different CV strategies.

## 1. KFold

Use for:

> Standard regression problems.

It divides the data into K folds and rotates which fold is used for validation.

## 2. StratifiedKFold

Use for:

> Classification.

It tries to preserve the **class ratios** in each fold.

For example, if the complete dataset is roughly:

```text
80% class A
20% class B
```

the folds try to maintain a similar ratio.

## 3. GroupKFold

Use when:

> Multiple rows belong to the same entity and must stay together.

For example, if many measurements come from the same entity, we do not want some measurements from that entity in training and other measurements from that same entity in validation.

## 4. TimeSeriesSplit

Use for:

> Time-ordered data.

The model should learn from the **past** and validate on the **future**.

We should not randomly mix future information into training.

## 5. Leave-One-Out

Each individual observation becomes the validation set once.

The session says it is mainly for:

- very small datasets
- but it can be expensive
- and can have high variance

## Always report the spread

The session gives the idea:

```text
0.85 ± 0.02
```

and

```text
0.85 ± 0.15
```

have the same mean but very different spread.

So:

> **Standard deviation across folds is part of the result.**
