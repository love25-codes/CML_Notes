https://cml-ayush.netlify.app/#1

# Machine Learning — Introduction

## 1. What is Machine Learning?

Machine Learning (ML) is a field where computers learn patterns or relationships from data/examples instead of being explicitly programmed with all the rules.

### Traditional Programming

**Rules + Data → Output**

The programmer manually defines the rules.

Example:

    IF email contains suspicious words
    THEN classify as SPAM

### Machine Learning

**Data + Correct Outputs → Rules (Model)**

The machine learns the rules/patterns from examples.

    Training Data
         ↓
    ML Algorithm
         ↓
    Learned Model

---

## 2. Traditional Programming vs Machine Learning

| Traditional Programming | Machine Learning |
|---|---|
| Rules are written by humans | Rules are learned from data |
| Rules + Data → Output | Data + Output → Model |
| Programmer specifies the logic | Algorithm discovers patterns |
| Works well when rules can be explicitly defined | Useful when rules are difficult to define manually |

### Key Idea

> Machine Learning is essentially **flipping traditional programming**: instead of manually writing all the rules, we provide examples and let the algorithm learn the rules.

---

## 3. What is a Model?

A **model** is a learned mathematical representation of the relationship between input data and output.

Example:

    House Area → House Price

Given enough examples, an ML algorithm might learn:

    Price = 5000 × Area

The values/parameters of the model are learned from the training data.

---

## 4. Mitchell's Definition of Machine Learning

Tom Mitchell's definition:

> A program learns from experience E with respect to a task T and performance measure P if its performance at T, as measured by P, improves with experience E.

There are three important components:

- **E = Experience**
- **T = Task**
- **P = Performance Measure**

### Spam Filter Example

For a spam detection system:

- **E (Experience)** = Labelled emails
- **T (Task)** = Flag/classify emails as spam or not spam
- **P (Performance)** = Fraction/percentage of emails correctly classified

If the system becomes better at classifying emails as it gets more experience, then it is learning.

---

## 5. Experience (E)

Experience is the information/examples from which the model learns.

Example:

    Email 1 → Spam
    Email 2 → Not Spam
    Email 3 → Spam
    Email 4 → Not Spam
    ...

These labelled examples become the model's experience.

---

## 6. Task (T)

The task is what we want the ML system to accomplish.

Examples:

- Detect spam emails
- Predict house prices
- Recognize handwritten digits
- Predict whether a customer will purchase a product

For a spam filter:

    New Email → Spam / Not Spam

---

## 7. Performance Measure (P)

The performance measure tells us **how well the model is performing**.

Example:

Suppose a model correctly classifies 92 out of 100 emails.

    Performance = 92 / 100 = 92%

If performance improves:

    92% → 95% → 97%

as the model gains experience, then the model is learning.

Different ML tasks use different performance measures.

Examples:

- Accuracy
- Precision
- Recall
- F1-score
- Mean Squared Error (MSE)
- Mean Absolute Error (MAE)

---

## 8. Training

**Training** is the process of learning a model from data.

    Training Data
          ↓
    ML Algorithm
          ↓
    Learned/Trained Model

During training, the algorithm tries to discover patterns or relationships in the data.

---

## 9. Prediction / Inference

After training, the model can be used to make predictions on new data.

    New Input
        ↓
    Trained Model
        ↓
    Prediction

Example:

    New Email
        ↓
    Trained Spam Model
        ↓
    "Spam"

### Training vs Prediction

| Training | Prediction/Inference |
|---|---|
| Model learns from data | Model uses what it learned |
| Uses training examples | Usually uses unseen/new data |
| Produces a trained model | Produces predictions |

---

## 10. Features and Labels

These are fundamental terms in Machine Learning.

### Features (X)

Features are the **input variables** used by the model to make predictions.

Example:

| Age | Income | Purchased |
|---:|---:|---|
| 22 | 30,000 | No |
| 35 | 80,000 | Yes |
| 42 | 100,000 | Yes |

Here:

    Features = Age, Income

Features are commonly represented as:

**X**

---

## 11. Label / Target (y)

The label or target is the value we want the model to predict.

In the above example:

    Target = Purchased

It is commonly represented as:

**y**

The basic relationship is:

    X → Model → ŷ

Where:

- **X** = Input features
- **y** = Actual target
- **ŷ (y-hat)** = Predicted target

---

## 12. Supervised Learning

In **Supervised Learning**, the training data contains both:

- Input/features
- Correct output/label

    Input + Correct Output
              ↓
         ML Algorithm
              ↓
            Model

Example:

    Email → Spam
    Email → Not Spam
    Email → Spam

The model learns the relationship:

    X → y

### Two Major Types of Supervised Learning

### A. Classification

Classification predicts a **category/class**.

Examples:

    Email → Spam / Not Spam
    Image → Cat / Dog
    Transaction → Fraud / Not Fraud
    Patient → Disease / No Disease

Output is usually discrete/categorical.

### B. Regression

Regression predicts a **continuous numerical value**.

Examples:

    House Features → House Price
    Experience → Salary
    Weather Data → Temperature

Example:

    House → ₹85,50,000

---

## 13. Unsupervised Learning

In **Unsupervised Learning**, the training data does not contain predefined labels.

    Data
     ↓
    ML Algorithm
     ↓
    Patterns / Structure

The algorithm tries to discover hidden patterns or structures in the data.

### Example: Customer Segmentation

Suppose we have:

- Age
- Income
- Spending
- Number of purchases

but we don't know the customer groups beforehand.

An algorithm can discover groups such as:

    Group 1 → Low-spending customers
    Group 2 → Regular customers
    Group 3 → High-value customers

A common unsupervised learning technique is:

**Clustering**

---

## 14. Generalization

A very important goal of Machine Learning is **generalization**.

Generalization means:

> The ability of a trained model to perform well on new, unseen data.

A model should not simply memorize the training examples.

    Training Data
          ↓
        Model
          ↓
    New/Unseen Data
          ↓
    Good Predictions

A model that performs well only on training data but poorly on new data has a problem called **overfitting**.

Related concepts:

- Overfitting
- Underfitting
- Train/Test Split
- Cross-Validation
- Regularization

---

## 15. Basic Machine Learning Pipeline

A typical ML workflow looks like:

    Dataset
       ↓
    Data Preprocessing
       ↓
    Train / Validation / Test Split
       ↓
    Choose ML Algorithm
       ↓
    Train Model
       ↓
    Evaluate Model
       ↓
    Tune/Improve Model
       ↓
    Make Predictions

---

## 16. Traditional Programming vs Machine Learning — Mental Model

### Traditional Programming

    Human-written Rules
            +
           Data
            ↓
          Output

### Machine Learning

           Data
            +
      Correct Outputs
            ↓
       ML Algorithm
            ↓
      Learned Rules / Model
            ↓
         New Data
            ↓
         Prediction

The **"flip" from manually writing rules to learning rules from examples** is the fundamental intuition behind Machine Learning.

---

## 17. Real-World Examples of Machine Learning

| Problem | Input | Output |
|---|---|---|
| Spam Detection | Email content | Spam / Not Spam |
| House Price Prediction | Area, rooms, location | Price |
| Fraud Detection | Transaction details | Fraud / Not Fraud |
| Recommendation System | User/item history | Recommended item |
| Image Classification | Image pixels | Class/category |
| Weather Prediction | Weather measurements | Temperature/rain/etc. |

---

## 18. Important Terms

- **Dataset** → Collection of data used for ML
- **Feature** → Input variable
- **Label/Target** → Output we want to predict
- **Model** → Learned representation/pattern
- **Training** → Learning from data
- **Prediction/Inference** → Using the trained model
- **Experience (E)** → Data/examples used for learning
- **Task (T)** → What the model needs to accomplish
- **Performance (P)** → How well the model performs
- **Generalization** → Performing well on unseen data
- **Classification** → Predicting categories
- **Regression** → Predicting numerical values
- **Clustering** → Finding groups in unlabeled data

---

## 19. Key Takeaways

1. Traditional programming:
   **Rules + Data → Output**

2. Machine Learning:
   **Data + Correct Outputs → Learned Rules/Model**

3. A model learns patterns/relationships from data.

4. Mitchell's definition has three components:
   **Experience (E), Task (T), Performance (P)**.

5. Features are inputs and are commonly represented by **X**.

6. Labels/targets are outputs and are commonly represented by **y**.

7. Predictions are commonly represented by **ŷ (y-hat)**.

8. Supervised learning uses labelled data.

9. Classification predicts categories.

10. Regression predicts numerical values.

11. Unsupervised learning works without predefined labels.

12. A good ML model should **generalize well to unseen data**.

13. The central idea of ML is:

    **Learn the rules from examples instead of manually programming every rule.**