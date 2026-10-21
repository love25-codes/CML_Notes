# 09 — Coefficient Paths

## What is a coefficient path?

A coefficient path shows how model coefficients change as λ changes.

Usually the horizontal axis is:

$$
\log(\lambda)
$$

## Ridge path

As λ increases:

> Ridge coefficients move smoothly toward zero.

They shrink gradually.

They do not suddenly disappear.

## Lasso path

As λ increases:

> Lasso coefficients can hit exactly zero.

Different coefficients can become zero at different values of λ.

Once a coefficient becomes zero, that feature is effectively removed from the model.

## Easy comparison

```text
Ridge:
large coefficient
      ↓
smaller
      ↓
smaller
      ↓
toward zero

Lasso:
large coefficient
      ↓
smaller
      ↓
0
```

## Why coefficient paths are useful

A coefficient-path graph lets you visually see the difference between:

- Ridge → smooth shrinkage
- Lasso → coefficients can disappear

## Memory trick

> **Ridge slides. Lasso snaps.**
