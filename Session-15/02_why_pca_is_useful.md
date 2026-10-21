# 2. Why PCA Is Useful

PCA connects to several common data problems:

- **Curse of dimensionality:** As the number of features grows, data points can become sparse and distances may become less useful.
- **Multicollinearity:** Some features are strongly related to one another. This can make regression coefficients unstable.
- **Visualisation:** We cannot directly draw data with dozens of features. PCA can project it into two or three dimensions.
- **Computational cost and noise:** Fewer dimensions can reduce memory and processing time, and removing low-variance directions sometimes removes noise.

PCA is useful, but it is not always the best choice. It can discard information that matters for predicting a target, especially when that information lies in a low-variance direction.
