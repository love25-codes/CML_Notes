# 6. PCA vs. Linear Regression

Although PCA and linear regression can both be shown as lines on a graph, they solve different problems.

| PCA | Linear regression |
|---|---|
| Does not require a target/output column. | Uses a target/output column. |
| Treats the input features symmetrically. | Predicts the target from input features. |
| Finds directions of maximum variance. | Finds a line that minimises prediction errors in the target direction. |
| Its geometric fit is based on perpendicular distances. | Ordinary regression minimises vertical errors in the target variable. |

**Simple way to remember:** Regression asks, “How can I predict Y?” PCA asks, “In which directions is my data spread out the most?”
