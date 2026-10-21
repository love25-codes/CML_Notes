# 7. Geometry: Prediction as a Projection

Think of the target vector `y` as a point/vector that may not lie inside the space that the features can represent.

The columns of `X` create a space called the **column space of X**.

The model can only produce predictions inside that space:

```text
ŷ = Xβ
```

The best prediction is the closest point in that space to `y`.

That closest point is the **orthogonal projection**.

The leftover vector:

```text
e = y - ŷ
```

is perpendicular to the feature space.

So:

```text
residual ⟂ column space of X
```

This is exactly why:

```text
Xᵀ(y - Xβ) = 0
```

## Simple picture in words

```text
y
      \  residual
         ŷ  ← closest point
    ───────── feature space
```

## Main idea
Linear regression is not just "drawing the best line."

Geometrically, it is:

> Projecting the target onto the space that can be created from the features.
