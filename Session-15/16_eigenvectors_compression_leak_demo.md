# 16. Demonstration: Directions, Compression, and Leakage

The lecture's demonstration is intended to make three ideas visible:

1. **Eigenvectors as axes:** draw principal directions over a cloud of data points. PC1 should align with the direction of greatest spread.
2. **Centring and scaling:** compare PCA results before and after preprocessing. Without suitable preprocessing, one feature or the location of the data can dominate PC1.
3. **Compression and reconstruction:** compare digit reconstructions made with 5, 20, 40, and 64 components. More components generally preserve more detail.
4. **Model comparison and leakage:** compare a full feature set with a reduced PCA representation, then show why fitting PCA before the train/test split produces an unfair evaluation.

The main lesson is not that PCA always improves accuracy. It is that PCA changes the representation, and all learned preprocessing steps must be fitted only on the training data.
