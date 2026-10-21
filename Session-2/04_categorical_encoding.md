# Categorical Encoding

## 1. Why do we encode?

Machine Learning models usually work with numbers.

But real data often contains categories:

```text
Delhi
Mumbai
Bangalore
```

We need to convert these categories into numerical representation.

## 2. One-hot encoding

Each category gets its own 0/1 column.

Example:

| City | Delhi | Mumbai | Bangalore |
|---|---:|---:|---:|
| Delhi | 1 | 0 | 0 |
| Mumbai | 0 | 1 | 0 |
| Bangalore | 0 | 0 | 1 |

This does **not** create a fake ordering.

## 3. Why not use 0, 1, 2?

Suppose:

```text
Delhi = 0
Mumbai = 1
Bangalore = 2
```

A linear or distance-based model may interpret this as:

```text
Delhi < Mumbai < Bangalore
```

But cities have no natural order.

This is called the **nominal trap**.

## 4. Ordinal encoding

Ordinal encoding is appropriate when categories really have an order.

Example:

```text
Low < Medium < High
```

Here numerical encoding makes sense.

## 5. Label encoding

Label encoding is generally appropriate for the **target variable**, not arbitrary categorical input features.

Example target:

```text
No  → 0
Yes → 1
```

## 6. High cardinality

Suppose a column contains 10,000 different cities.

One-hot encoding can create around 10,000 columns.

That can become inefficient.

For high-cardinality features, techniques such as frequency encoding or target encoding may be considered.

## 7. Dummy-variable trap

If there are `k` categories, one-hot encoding creates `k` columns.

For every row:

```text
dummy_1 + dummy_2 + ... + dummy_k = 1
```

If a linear model also has an intercept, the columns become perfectly linearly dependent.

This can make the matrix singular and cause problems for ordinary linear regression.

Common fix for linear models:

```python
OneHotEncoder(drop="first")
```

or, in suitable pandas workflows:

```python
pd.get_dummies(..., drop_first=True)
```

The session notes that trees and Ridge are not affected in the same way by this particular dummy-variable issue.

## 8. Unknown categories

A test set may contain a category that was never seen during training.

Example:

Training:

```text
Delhi
Mumbai
```

Test:

```text
Delhi
Bangalore
```

`Bangalore` is unknown to the encoder.

A useful sklearn setting is:

```python
OneHotEncoder(handle_unknown="ignore")
```

This prevents the encoder from crashing because of an unseen category.

## 9. Exam memory

- Nominal category → One-hot
- Ordered category → Ordinal encoding
- Target → Label encoding can be appropriate
- Many categories → consider high-cardinality methods
- Unknown test category → `handle_unknown="ignore"`
