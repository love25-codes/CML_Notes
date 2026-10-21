# 07 — Polynomial Complexity and Scaling

## 1. Complexity can grow very quickly

Polynomial regression becomes expensive as the number of original features and the degree increase.

The session gives the number of polynomial terms as:

\[
\binom{p+d}{d}
\]

where:

- `p` = number of original features
- `d` = polynomial degree

## 2. Example from the session

For:

```text
p = 5 features
d = 3
```

the number of polynomial terms is:

\[
\binom{5+3}{3}
=
\binom{8}{3}
=
56
\]

So five original features can turn into **56 columns** for degree 3.

That is a big increase.

## 3. Why does this matter?

More columns mean a much more flexible model.

That can lead to:

- higher computational cost
- more opportunity to fit noise
- higher variance

The session explicitly notes:

> More columns → more variance.

## 4. Scaling becomes important

Polynomial features can create very large numerical values.

For example, if:

```text
x = 100
```

then:

```text
x²  = 10,000
x⁵  = 10,000,000,000
x¹⁵ = extremely large
```

So high-degree polynomial features can produce very different numerical scales.

The session warns that an unscaled `x^15` can produce catastrophic numerical ranges.

## 5. Practical rule

The session gives a very useful rule:

> Polynomial features and a scaler travel together — always.

In practice, the workflow is conceptually:

```text
Original features
      ↓
Polynomial features
      ↓
Scaling
      ↓
Regression model
```

The exact implementation can vary, but the important idea is to prevent polynomial columns from having wildly different scales.

## 6. Memory trick

Remember:

```text
Higher degree
→ more features
→ more flexibility
→ potentially more variance
→ scaling becomes important
```

## 7. Exam shortcut

If a question says:

> "degree increased from 2 to 15"

Think:

- complexity increases
- bias tends to decrease
- variance tends to increase
- overfitting becomes more possible
- polynomial feature magnitudes can become very large
