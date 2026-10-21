# ML Pipeline — The Two Boxes Beginners Skip

## 1. Big Picture

A real Machine Learning project has two important edges:

```text
Business Problem
       ↓
   ML Pipeline
       ↓
   Monitoring
```

The middle contains the mathematical/modeling part of the ML course.

> The value of an ML model is determined not only by the model itself, but also by whether we are solving the right business problem and whether the model continues to work after deployment.

---

# 2. First Box — Business Problem

Many ML projects fail because the **problem was poorly defined**, not because the algorithm was bad.

Common problems:

- Wrong question
- Poorly defined target
- Target cannot be acted upon
- No agreed performance metric
- ML solution does not actually solve the business need

### Example

Business problem:

```text
Reduce customer churn
```

This is not yet a precise ML problem.

We can formulate it as:

```text
Predict whether a customer will cancel their subscription
within the next 30 days.
```

Now it becomes a clear ML problem.

---

# 3. Business Problem → ML Problem

A business problem needs to be converted into a precise ML problem.

```text
Business Goal
     ↓
Define ML Task
     ↓
Define Target
     ↓
Define Features
     ↓
Define Success Metric
```

### Questions to ask

1. What exactly are we trying to solve?
2. What are we predicting?
3. What is the target/label `y`?
4. What features `X` are available?
5. Can the prediction lead to an action?
6. How will we measure success?

---

# 4. Target Definition

The target must be precisely defined.

Example:

```text
Target:
Will the customer churn within the next 30 days?
```

Then:

```text
X = Customer information
y = Churn / No Churn
```

This becomes a supervised classification problem.

A poorly defined target can make an otherwise technically good model useless.

---

# 5. Actionability

A prediction is valuable when it can lead to an action.

Example:

```text
Model Prediction
      ↓
90% chance customer will churn
      ↓
Send retention offer
      ↓
Customer stays
      ↓
Business benefit
```

Therefore:

```text
Prediction → Action → Business Outcome
```

If nobody can act on the prediction, the model may have little practical value.

---

# 6. Choosing the Right Metric

A model needs a clearly defined performance metric.

The business and ML team should agree on what "good performance" means.

Possible metrics include:

### Classification

- Accuracy
- Precision
- Recall
- F1-score
- ROC-AUC

### Regression

- MAE
- MSE
- RMSE
- R²

### Important Example

Suppose 99% of emails are not spam.

A model that predicts:

```text
Everything → Not Spam
```

could achieve approximately 99% accuracy while being useless at detecting spam.

Therefore, **accuracy is not always the right metric**.

---

# 7. The Middle of the Pipeline

The ML/modeling pipeline can include:

```text
Business Problem
       ↓
Data Collection
       ↓
Data Cleaning
       ↓
Feature Engineering
       ↓
Train/Test Split
       ↓
Model Selection
       ↓
Training
       ↓
Evaluation
       ↓
Deployment
```

Classical ML studies many concepts in this middle section:

- Linear Regression
- Logistic Regression
- KNN
- Decision Trees
- Random Forest
- SVM
- Naive Bayes
- Clustering
- PCA
- Gradient Descent
- Loss Functions
- Regularization
- Cross-Validation
- Feature Engineering
- Model Evaluation

---

# 8. Last Box — Monitoring

A model is **not finished when it is deployed**.

Real-world data changes over time.

```text
Train Model
     ↓
Deploy
     ↓
Monitor
     ↓
Detect Problems
     ↓
Retrain / Update
     ↓
Redeploy
```

This makes ML an ongoing lifecycle rather than a one-time task.

---

# 9. Data Drift

**Data drift** occurs when the distribution of input data changes over time.

Example:

During training:

```text
Average customer age = 25
```

After deployment:

```text
Average customer age = 40
```

The input data distribution has changed.

Mathematically, data drift can be thought of as a change in:

```text
P(X)
```

where `X` represents the input/features.

### Simple definition

> Data drift = The input data changes over time.

---

# 10. Concept Drift

**Concept drift** occurs when the relationship between the input and target changes.

Mathematically:

```text
P(y | X) changes
```

Example:

A customer's behavior that previously indicated they would purchase a product may no longer indicate the same thing because customer preferences have changed.

### Simple definition

> Concept drift = The relationship between input `X` and target `y` changes.

---

# 11. Data Drift vs Concept Drift

| Data Drift | Concept Drift |
|---|---|
| Input distribution changes | Relationship between X and y changes |
| `P(X)` changes | `P(y \| X)` changes |
| Data itself looks different | Meaning/predictive relationship changes |
| Can cause model degradation | Can cause model degradation |

### Easy Memory Trick

```text
Data Drift    → DATA changed
Concept Drift → RELATIONSHIP changed
```

---

# 12. Model Decay

A model can become less accurate over time.

Example:

```text
Initial accuracy → 95%
       ↓
After some time → 91%
       ↓
Later → 84%
```

Possible reasons:

- Data drift
- Concept drift
- Changes in user behavior
- Changes in market conditions
- Seasonal changes
- Changes in product/service
- Changes in external conditions

This gradual loss of effectiveness is called **model decay**.

---

# 13. What Should Be Monitored?

## Data Monitoring

Check whether incoming data has changed.

Examples:

- Feature distributions
- Missing values
- Outliers
- Data ranges
- Category frequencies

## Model Performance Monitoring

Track metrics such as:

- Accuracy
- Precision
- Recall
- F1-score
- MAE
- RMSE

depending on the problem.

## Prediction Monitoring

Check whether model predictions are behaving unexpectedly.

Example:

```text
Previously:
8% of predictions = Spam

Now:
45% of predictions = Spam
```

This could indicate a problem requiring investigation.

## System Monitoring

Also monitor technical metrics:

- Latency
- CPU usage
- Memory
- Request failures
- Throughput

---

# 14. ML Lifecycle

A production ML system is often an iterative loop:

```text
Business Problem
       ↓
Problem Formulation
       ↓
Data Collection
       ↓
Data Preparation
       ↓
Feature Engineering
       ↓
Model Training
       ↓
Evaluation
       ↓
Deployment
       ↓
Monitoring
       ↓
Detect Drift / Performance Drop
       ↓
Retraining
       ↓
Redeployment
       ↓
Monitoring
       ↺
```

The process does not necessarily end after deployment.

---

# 15. Real-World Example — Customer Churn

### Business Problem

```text
Company wants to reduce customer churn.
```

### ML Problem

```text
Predict whether a customer will churn within 30 days.
```

### Features

```text
X:
- Number of purchases
- Days since last purchase
- Average order value
- Number of support tickets
- Login frequency
```

### Target

```text
y:
Churn / No Churn
```

### Model

Example:

```text
Logistic Regression
```

### Evaluation

Possible metrics:

```text
Precision
Recall
F1-score
```

### Action

```text
High churn probability
        ↓
Retention offer
        ↓
Customer may stay
```

### Monitoring

After deployment:

```text
Monitor input data
       +
Monitor predictions
       +
Monitor model performance
```

If performance decreases:

```text
Detect drift
     ↓
Investigate
     ↓
Retrain
     ↓
Redeploy
```

---

# 16. Two Most Important Questions

### Before building the model:

> **Are we solving the right problem?**

### After deploying the model:

> **Is the model still solving the problem correctly?**

---

# 17. Key Takeaways

1. ML projects do not start with choosing an algorithm.

2. First, clearly define the **business problem**.

3. Convert the business problem into a precise **ML problem**.

4. Define the target `y` carefully.

5. The prediction should ideally lead to an **actionable decision**.

6. Define the performance metric before deciding whether a model is "good".

7. Deployment is **not the end** of an ML project.

8. Real-world data changes over time.

9. **Data drift** means the input distribution `P(X)` changes.

10. **Concept drift** means the relationship `P(y | X)` changes.

11. **Model decay** occurs when model effectiveness decreases over time.

12. Production ML requires continuous **monitoring**.

13. If performance decreases, the model may need investigation, retraining, and redeployment.

14. The ML lifecycle is a **loop**, not simply a straight line.

### One-line mental model

**Right Problem → Good Data → Good Model → Correct Action → Continuous Monitoring**