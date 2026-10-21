# 02 — Add a Price for Complexity

## Main idea

Regularization changes the objective function.

Instead of only minimizing the prediction error, we minimize:

$$
\text{Loss} = \text{MSE} + \lambda \times \text{Penalty}(\beta)
$$

### What does this mean?

- **MSE** = how wrong the model's predictions are.
- **Penalty** = how complicated / large the coefficients are.
- **λ (lambda)** = controls how strongly we care about the penalty.
- **β (beta)** = model coefficients.

So the model is solving two problems at once:

> Fit the data well, but also avoid unnecessarily large coefficients.

## The trade-off

Regularization intentionally accepts a little more **bias** if that gives a large reduction in **variance**.

This connects directly to the bias-variance idea:

- Too much flexibility → high variance → overfitting.
- Regularization reduces that flexibility.
- Therefore variance can decrease.
- But bias can increase.

## Easy way to remember

Think of λ as a **strictness knob**.

- Small λ → weak punishment.
- Large λ → strong punishment.
