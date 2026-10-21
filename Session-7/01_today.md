# 01 — Where We Are Going Today

## What this session is about

This session is about **Regularization** and **Cross-Validation**.

The main goals are:

1. Understand **Ridge Regression**.
2. Understand **Lasso Regression**.
3. Understand **Elastic Net**.
4. Understand why **L1 regularization can make coefficients exactly zero**.
5. Understand **K-Fold Cross-Validation**.
6. Learn how to tune hyperparameters without causing **data leakage**.

## Why do we need regularization?

In an earlier high-degree polynomial model, the model could have **very large coefficients** that almost cancel each other.

That can create a very wiggly model.

The simple idea is:

> If coefficients become unnecessarily large, make the model pay a penalty.

That penalty is called **regularization**.

Regularization is mainly used to control **overfitting / variance**.
