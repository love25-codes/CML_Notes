# 10 — Regularization: The Bridge to the Next Topic

## 1. Why is regularization mentioned here?

The session ends by connecting bias–variance to the next set of topics.

The problem is:

> We cannot directly compute bias and variance from one dataset because their definitions involve many possible training datasets.

So instead of directly measuring them, we can impose structure on the class of functions the model is allowed to fit.

## 2. What does "impose structure" mean?

It means:

> Put some restriction on the model so it cannot behave in completely unrestricted ways.

For example, instead of allowing a model to create extremely large coefficients and very wiggly predictions, we can penalize large coefficients.

This idea leads to regularization.

## 3. Why can this help?

A very flexible model can have high variance.

Restricting the model can make it less sensitive to individual training observations.

Conceptually:

```text
Very flexible model
        ↓
can chase noise
        ↓
high variance
```

With a constraint:

```text
Restrict model complexity
        ↓
less ability to chase noise
        ↓
variance can decrease
```

There is a trade-off: making a model more restricted can increase bias.

## 4. The session's broader idea

The session says that:

- regularization
- pruning
- ensembling

are all ways of imposing structure or controlling model behavior to strike a useful balance.

## 5. Why this matters for polynomial regression

Polynomial degree controls one kind of complexity.

For example:

```text
degree 1 → simple
degree 3 → more flexible
degree 15 → very flexible
```

Regularization provides another way to control a flexible model.

Instead of necessarily throwing away polynomial features, we can constrain their coefficients.

## 6. Connection to the next topic

The session ends with the question:

> If large coefficients cause the wiggles, what if we simply penalised large coefficients?

That is the bridge to regularization.

The important idea for now is:

```text
Control complexity
→ control variance
→ balance bias and variance
```
