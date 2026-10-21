# 15. Checkpoint: “Great Results—but Wrong”

Question: “I ran PCA on all my data, then split it into training and test sets, and got great results. What is wrong?”

The problem is **data leakage**. PCA has already learned the data's mean and principal directions using both training and test examples. The test set has influenced the transformation, so it is no longer a fully independent evaluation.

Even if PCA does not use the target labels, it still learns information from the feature values. The correct approach is to split first, fit PCA only on training data, and use that fitted PCA to transform the test data.
