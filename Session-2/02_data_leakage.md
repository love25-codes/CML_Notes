# Data Leakage

## 1. Simple meaning

**Data leakage means the model gets information that it should NOT have at prediction time.**

Think of an exam:

- Training data = practice questions
- Test data = final exam
- Leakage = secretly looking at the final exam answers while preparing

The result looks very good, but it is dishonest and will fail in real life.

## 2. Main symptom

Be suspicious when:
- validation accuracy is unbelievably high
- one feature almost perfectly predicts the target
- notebook performance is excellent but production performance is poor

## 3. Three leakage patterns

### A. Preprocessing leakage

Wrong:

```text
Entire dataset
      ↓
Fit scaler
      ↓
Train/test split
```

The scaler has learned information from the test set.

Correct:

```text
Train/test split
      ↓
Fit scaler on TRAIN only
      ↓
Transform train and test
```

### Why?

A scaler learns values such as:
- mean
- standard deviation
- minimum
- maximum

If these are calculated using test data, test information has entered training.

---

### B. Target leakage

A feature contains information that is only available **after the outcome happens**.

Example:

You want to predict:

```text
will_default
```

But you use:

```text
total_amount_recovered
```

The recovery amount is known only after the person has already defaulted.

So the model is effectively seeing the answer.

---

### C. Temporal leakage

This happens with time-based data.

Suppose we want to predict what happened in January.

If a random split allows the model to train on February/March data, the model can see the future.

Correct approach for time-dependent problems:

```text
Past → Train
Future → Validation/Test
```

Do not randomly mix past and future when the timeline matters.

## 4. Common root cause

All three types have the same basic problem:

> Information crossed a boundary it should not have crossed.

- Test → Train = preprocessing leakage
- Future → Past = temporal leakage
- After outcome → Before outcome = target leakage

## 5. Important rule

**Split first. Fit preprocessing second.**

## 6. Interview answer

**Q: What is data leakage?**

Data leakage occurs when information that would not be available at prediction time is used during model training. It can cause unrealistically high validation performance and poor production performance.

**Q: Name three types.**

1. Preprocessing leakage
2. Target leakage
3. Temporal leakage
