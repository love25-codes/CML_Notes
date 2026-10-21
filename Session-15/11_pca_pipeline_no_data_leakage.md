# 11. PCA in a Pipeline: Avoid Data Leakage

**Data leakage** happens when information from the test set is used while training or preparing the model. This can make test results look better than they really are.

PCA learns the mean, component directions, and variance structure from the data. Therefore, PCA must not be fitted using the test set.

## Correct order
1. Split the data into training and test sets.
2. Fit scaling/preprocessing on the training set.
3. Fit PCA on the processed training set.
4. Train the model on the transformed training data.
5. Transform the test data using the already-fitted scaler and PCA.
6. Evaluate the model on the transformed test data.

Do **not** run PCA on the complete dataset before splitting. That allows test-set information to influence the components.

## Limitation
Principal components can be hard to interpret because each is a combination of original features. If stakeholders need clear explanations about individual features, PCA may make interpretation more difficult.
