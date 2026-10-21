# Machine Learning — Types of Learning

## 1. Machine Learning Taxonomy

Machine Learning can be broadly categorized according to the type of feedback/data available during learning.

```text
                         MACHINE LEARNING
                                │
          ┌─────────────────────┼─────────────────────┐
          ↓                     ↓                     ↓
    SUPERVISED           UNSUPERVISED         OTHER PARADIGMS
    Has labels            No labels             Semi-supervised
                                                Reinforcement
```

> The exact taxonomy can vary between textbooks. A common modern view includes supervised, unsupervised, semi-supervised, and reinforcement learning.

---

# 2. Supervised Learning

In supervised learning, the dataset contains:

- Features/input `X`
- Label/target `y`

The goal is to learn the mapping:

```text
X → y
```

The model learns from examples where the correct answer is already known.

### Example

| Hours Studied (X) | Exam Score (y) |
|---:|---:|
| 2 | 40 |
| 4 | 55 |
| 6 | 70 |
| 8 | 85 |

The model learns the relationship between study hours and exam score.

For a new input:

```text
8 hours → ?
```

the model predicts the output.

### Why "Supervised"?

The labelled data acts like a teacher/supervisor because the correct answer is provided during training.

---

# 3. Types of Supervised Learning

There are two major types:

```text
Supervised Learning
       │
       ├── Regression
       │
       └── Classification
```

## 3.1 Regression

Regression is used when the target is a continuous numerical value.

Examples:

- House features → House price
- Experience → Salary
- Weather data → Temperature
- Area → Electricity consumption

Example:

```text
House → ₹75,00,000
```

### Intuition

> Regression = "How much?" / "How many?"

---

## 3.2 Classification

Classification is used when the target belongs to a category/class.

Examples:

```text
Email → Spam / Not Spam

Transaction → Fraud / Not Fraud

Image → Cat / Dog

Customer → Churn / No Churn
```

### Intuition

> Classification = "Which category?"

---

# 4. Regression vs Classification

| | Regression | Classification |
|---|---|---|
| Output | Numerical | Categorical |
| Example | House price | Spam detection |
| Output example | ₹75 lakh | Spam |
| Main question | How much? | Which class? |
| Type | Continuous | Discrete/Categorical |

### Important

The type of supervised learning is mainly determined by the **target/output `y`**.

---

# 5. Unsupervised Learning

In unsupervised learning, the dataset contains:

```text
Features X
```

but there is **no predefined target y**.

So:

```text
Supervised   → X + y
Unsupervised → X only
```

The goal is to discover patterns, structure, or relationships that already exist in the data.

```text
Data
 ↓
ML Algorithm
 ↓
Discover Structure
```

---

# 6. Clustering

Clustering is an important unsupervised learning technique.

Its goal is to group similar data points together.

Example:

```text
Customer Data
      ↓
   Clustering
      ↓
 ┌────┼────┐
 ↓    ↓    ↓
G1   G2   G3
```

Possible groups:

- Budget customers
- Regular customers
- Premium customers

The algorithm is not given these group labels beforehand.

It discovers groups based on similarity.

### Important

The algorithm may simply produce:

```text
Cluster 1
Cluster 2
Cluster 3
```

Humans can later analyze the clusters and assign meaningful names.

---

# 7. PCA

PCA stands for **Principal Component Analysis**.

PCA is an unsupervised technique mainly used for:

- Dimensionality reduction
- Data visualization
- Removing redundant information
- Making high-dimensional data easier to work with

Example:

```text
100 Features
     ↓
    PCA
     ↓
10 Principal Components
```

PCA tries to represent the data using fewer dimensions while preserving as much important variation/information as possible.

Important PCA concepts to learn later:

- Variance
- Covariance
- Eigenvectors
- Eigenvalues
- Principal Components
- Explained Variance

---

# 8. Semi-Supervised Learning

Semi-supervised learning uses:

- A small amount of labelled data
- A large amount of unlabelled data

```text
Few labelled examples
          +
Many unlabelled examples
          ↓
        Model
```

Example:

Suppose there are 10,000 images.

```text
100 images → labelled
9,900 images → unlabelled
```

Instead of manually labelling all 10,000 images, the model tries to use both labelled and unlabelled data.

### Intuition

> Semi-supervised learning = A little supervision + lots of unlabelled data.

This is useful when obtaining labels is expensive or time-consuming.

---

# 9. Reinforcement Learning

Reinforcement Learning (RL) is based on learning through **rewards and penalties**.

Instead of being given the correct answer for every situation, an agent interacts with an environment and receives feedback.

```text
      Agent
        ↓
      Action
        ↓
   Environment
        ↓
  Reward/Penalty
        ↓
      Agent
```

Example:

```text
Good action → +10 reward
Bad action  → -5 reward
Winning     → +100 reward
Losing      → -100 reward
```

The agent learns which actions tend to produce higher rewards.

### Important RL Terms

| Term | Meaning |
|---|---|
| Agent | Learner/decision maker |
| Environment | World in which the agent operates |
| State | Current situation |
| Action | What the agent does |
| Reward | Feedback received |
| Policy | Strategy for choosing actions |

Applications include:

- Robotics
- Game playing
- Control systems
- Decision-making

---

# 10. Comparison of Learning Types

| Learning Type | Data | Main Goal | Example |
|---|---|---|---|
| Supervised | X + y | Learn X → y | Spam detection |
| Unsupervised | X only | Discover structure | Customer clustering |
| Semi-supervised | Few X + y, many X | Use both labelled and unlabelled data | Image classification |
| Reinforcement | State, action, reward | Learn best actions | Game-playing agent |

---

# 11. Easy Mental Model

### Supervised Learning

```text
Data + Correct Answers
          ↓
        Model
          ↓
      Prediction
```

The model learns from labelled examples.

### Unsupervised Learning

```text
Data Only
   ↓
 Model
   ↓
Discover Structure
```

The model discovers patterns without predefined labels.

### Semi-Supervised Learning

```text
Few labelled examples
          +
Many unlabelled examples
          ↓
        Model
```

### Reinforcement Learning

```text
State
 ↓
Action
 ↓
Environment
 ↓
Reward/Penalty
 ↓
Learn Policy
```

---

# 12. Learning the Mapping X → y

In supervised learning, the model tries to learn a function:

```text
f(X) ≈ y
```

After training:

```text
ŷ = f(X)
```

Where:

- `X` = input/features
- `y` = actual target
- `ŷ` = predicted target
- `f` = learned function/model

Example:

```text
ŷ = 8X + 20
```

If:

```text
X = 5
```

then:

```text
ŷ = 8(5) + 20
ŷ = 60
```

The model predicts `60`.

---

# 13. Why Semi-Supervised Learning is Useful

Obtaining labelled data can be expensive.

For example, medical images may require experts to provide labels:

```text
X-ray → Disease
X-ray → No Disease
```

Getting thousands of expert-labelled images can be expensive and time-consuming.

However, obtaining unlabelled images may be much easier.

Semi-supervised learning can use:

```text
Small labelled dataset
        +
Large unlabelled dataset
```

---

# 14. Key Differences

## Supervised vs Unsupervised

```text
Supervised:
X + y
↓
Learn X → y

Unsupervised:
X only
↓
Discover structure
```

## Supervised vs Reinforcement

```text
Supervised:
Correct answer is provided.

Reinforcement:
Feedback/reward is provided.
```

In supervised learning, the model is explicitly shown the desired output.

In reinforcement learning, the agent learns through consequences of its actions.

---

# 15. Important Terms

- **Feature (`X`)** → Input variable
- **Target/Label (`y`)** → Correct output
- **Prediction (`ŷ`)** → Model's predicted output
- **Supervised Learning** → Learning from labelled data
- **Regression** → Predicting continuous numerical values
- **Classification** → Predicting categories/classes
- **Unsupervised Learning** → Learning from unlabelled data
- **Clustering** → Grouping similar data points
- **PCA** → Principal Component Analysis; dimensionality reduction technique
- **Semi-Supervised Learning** → Learning using both labelled and unlabelled data
- **Reinforcement Learning** → Learning through rewards and penalties
- **Agent** → Decision-making entity in RL
- **Environment** → World in which the RL agent acts
- **Reward** → Feedback received by an RL agent
- **Policy** → Strategy used by an RL agent

---

# 16. Key Takeaways

1. **Supervised Learning** has labelled data:
   `X + y`

2. Supervised learning learns the mapping:
   `X → y`

3. **Regression** predicts numerical values.

4. **Classification** predicts categories.

5. **Unsupervised Learning** has no target:
   `X only`

6. **Clustering** groups similar data points.

7. **PCA** is mainly used for dimensionality reduction.

8. **Semi-Supervised Learning** uses a small amount of labelled data and a large amount of unlabelled data.

9. **Reinforcement Learning** learns through rewards and penalties.

10. The main distinction between these learning paradigms is **what kind of feedback/information the model receives**.

### One-line memory trick

```text
Supervised      → Learn from ANSWERS
Unsupervised    → Find PATTERNS
Semi-supervised → Few ANSWERS + lots of DATA
Reinforcement   → Learn from REWARDS
```