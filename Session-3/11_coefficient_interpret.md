# 11. Interpreting Linear Regression Coefficients

Example model:

```text
price = 2.1 + 0.85 × rooms - 0.30 × distance
```

Suppose:
- price is measured in ₹ lakh
- rooms is a count
- distance is measured in km

## Interpret the rooms coefficient

`0.85` means:

> Holding distance fixed, one additional room is associated with an increase of ₹0.85 lakh in predicted price.

## Interpret the distance coefficient

`-0.30` means:

> Holding the number of rooms fixed, one additional km from the centre is associated with a decrease of ₹0.30 lakh in predicted price.

## Why "holding other features fixed" matters

A coefficient describes the effect of changing one feature while keeping the others constant.

But if features strongly move together, this interpretation can become unreliable.

For example:

```text
rooms ↑
floor area ↑
```

If rooms and floor area are highly related, it may be difficult to isolate the effect of rooms alone.

This is the connection to multicollinearity.

## Interview-ready sentence

> A regression coefficient is the change in predicted target for a one-unit increase in that feature, holding the other included features constant.
