# 13. PCA and Multicollinearity

**Multicollinearity** means two or more features are strongly related. In regression, this can make it difficult to estimate stable coefficients for the original features.

PCA creates components that are uncorrelated with one another on the data used to fit it. Using these components instead of the original correlated features can reduce multicollinearity-related instability.

PCA also relates to the **curse of dimensionality**: reducing many features to fewer components can make distance-based methods such as KNN more practical.

However, components are not the same as the original features, so their meaning may be less obvious. PCA does not automatically guarantee better predictions; compare results using a valid train/test procedure.
