# Data Preparation for ML — Overview

## 1. What is data preparation?

Before giving data to a Machine Learning model, we usually need to clean and transform it.

Typical flow:

Raw Data → Split → Impute Missing Values → Encode Categories → Scale Features → Train Model

The goal is to make the data usable **without leaking information from the test set into training**.

## 2. Why is it important?

Many ML problems are caused by bad data preparation rather than a bad model.

The most important rule in this session is:

> **Anything that learns a value from the data must learn it from training data only.**

Examples:
- Mean used for imputation → calculate it from training data only.
- Standard deviation used for scaling → calculate it from training data only.
- Categories learned by an encoder → learn them from training data only.

## 3. Topics in this session

1. Data leakage
2. Missing values
3. MCAR, MAR and MNAR
4. Categorical encoding
5. Dummy-variable trap
6. Feature scaling
7. sklearn Pipeline and ColumnTransformer

## 4. Exam memory line

**Split first, then fit preprocessing on train only.**
