# sklearn Pipeline and ColumnTransformer

## 1. Why do we need a Pipeline?

A real ML project may need several preprocessing steps:

```text
Missing values
      ↓
Encoding
      ↓
Scaling
      ↓
Model
```

Doing all of this manually increases the chance of mistakes and leakage.

A Pipeline combines the steps into one object.

## 2. Basic idea

```text
Raw data
   ↓
Impute
   ↓
Encode
   ↓
Scale
   ↓
Model
```

The important part is that the Pipeline knows how to fit the preprocessing steps.

## 3. Why does it prevent leakage?

When we run:

```python
pipeline.fit(X_train, y_train)
```

the preprocessing transformers are fitted using training data.

Then:

```python
pipeline.predict(X_test)
```

uses the already learned preprocessing parameters to transform the test data.

The test data does not get used to learn the preprocessing parameters.

## 4. Typical example

```python
from sklearn.pipeline import Pipeline
from sklearn.impute import SimpleImputer
from sklearn.preprocessing import StandardScaler
from sklearn.linear_model import LogisticRegression

pipeline = Pipeline([
    ("imputer", SimpleImputer(strategy="median")),
    ("scaler", StandardScaler()),
    ("model", LogisticRegression())
])

pipeline.fit(X_train, y_train)
predictions = pipeline.predict(X_test)
```

## 5. ColumnTransformer

Different columns often need different treatment.

Example:

### Numerical columns

```text
Age
Salary
```

Could use:

```text
Impute → Scale
```

### Categorical columns

```text
City
JobType
```

Could use:

```text
Impute → One-hot encode
```

ColumnTransformer allows us to create both branches and combine them.

Conceptually:

```text
                 ┌→ Numerical → Impute → Scale ─┐
Raw data ────────┤                                ├→ Model
                 └→ Categorical → Impute → OneHot┘
```

## 6. Important rule

Every transformer that learns something must be fitted only on training data.

Examples:

- `SimpleImputer`
- `StandardScaler`
- `MinMaxScaler`
- `RobustScaler`
- `OneHotEncoder`

## 7. The whole safe workflow

```text
1. Split data
        ↓
2. Build preprocessing
        ↓
3. Put preprocessing + model in Pipeline
        ↓
4. Fit Pipeline on training data
        ↓
5. Predict on test data
        ↓
6. Evaluate
```

## 8. One-line interview answer

> A Pipeline prevents preprocessing leakage by fitting each transformer only on the training fold and then applying the learned transformation to validation/test data.

## 9. Important sklearn setting

For categorical variables:

```python
OneHotEncoder(handle_unknown="ignore")
```

This handles categories appearing in test data that were not present during training.

## 10. Final mental model

Think:

> **Split first. Learn preprocessing from train only. Apply the learned preprocessing everywhere else. Let Pipeline enforce this automatically.**
