# Missing Values

## 1. What are missing values?

A missing value means a data point is not available.

Example:

| Age | Salary |
|---:|---:|
| 20 | 30000 |
| 21 | NaN |
| 22 | 45000 |

`NaN` means the salary is missing.

## 2. What can we do?

We can either:
- remove data
- fill/impute the missing value

This session mainly focuses on imputation.

## 3. Numerical features

For numerical data, common choices are:

- Mean
- Median
- Constant value

### Mean

```text
mean = sum of values / number of values
```

Example:

```text
10, 20, 30

mean = 20
```

### Median

Median is the middle value after sorting.

Example:

```text
10, 20, 30
median = 20
```

## 4. Mean vs median

Prefer **median when strong outliers exist**.

Example:

```text
20, 22, 24, 25, 1000
```

The value `1000` pulls the mean upward.

The median remains much more representative of normal observations.

Memory trick:

> **Mean gets pulled by outliers; median is more resistant.**

## 5. Categorical features

For categorical data, use:

- Mode
- Explicit category such as `"Unknown"`

Example:

```text
City:
Delhi
Mumbai
NaN
Delhi
```

Possible replacement:

```text
Delhi
Mumbai
Delhi
Delhi
```

or:

```text
Delhi
Mumbai
Unknown
Delhi
```

## 6. was_missing flag

Sometimes the fact that a value was missing contains useful information.

Create another column:

```text
was_missing
```

Example:

| Income | was_missing |
|---:|---:|
| 50000 | 0 |
| 50000 | 1 |

The model can then learn whether missingness itself is meaningful.

## 7. Missingness mechanisms

### MCAR — Missing Completely At Random

Missingness is unrelated to everything.

Example idea:

A few forms are randomly damaged.

Dropping rows can be statistically safe, although it wastes data.

### MAR — Missing At Random

Missingness depends on information that we can observe.

Example:

Salary is more often missing for a certain observed job category.

Other observed features can help with imputation.

### MNAR — Missing Not At Random

Missingness depends on the missing value itself.

Example:

High-income people are more likely to refuse to report their income.

Simply filling the missing values with the mean can create bias.

## 8. Important warning

Mean imputation is convenient, but it can:
- reduce variance
- weaken correlations
- change the original distribution

## 9. Exam memory

**MCAR:** random

**MAR:** depends on observed information

**MNAR:** depends on the missing value itself

**Median:** useful when outliers exist
