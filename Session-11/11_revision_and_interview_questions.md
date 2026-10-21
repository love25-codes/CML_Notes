# 11. Revision Summary and Practice Questions

## Quick recap

-   **Pre-pruning:** Stop a tree early using limits such as `max_depth`.
-   **Post-pruning:** Grow the tree first, then remove branches.
-   **Cost-complexity pruning:** Balance tree error against the number
    of leaves using `ccp_alpha`.
-   **Pruning path:** Lists alpha values where the tree changes;
    cross-validation helps choose one.
-   **Numeric features:** Trees test thresholds between sorted values.
-   **Categorical features:** One-hot and ordinal encoding have
    different trade-offs; some libraries support categoricals natively.
-   **Missing values:** Handling depends on the implementation; options
    include imputation, surrogate splits, or learned default directions.
-   **MDI:** Adds up impurity reduction credited to each feature; can be
    biased.
-   **Permutation importance:** Measures validation-score drop after
    shuffling one feature.
-   **Interpretability:** A prediction can be explained by tracing its
    path from root to leaf.

## Interview-style questions

1.  What is the difference between pre-pruning and post-pruning?
2.  In (R\_`\alpha`{=tex}(T)=R(T)+`\alpha`{=tex}\|T\|), what does alpha
    penalise?
3.  Why can a one-hot encoded feature with many categories lead to
    fragmented splits?
4.  Why might an ID column receive high MDI importance?
5.  How is permutation importance calculated?
6.  Why does high feature importance not mean a feature causes the
    outcome?
7.  What do `gini`, `samples`, `value`, and `class` mean in a tree plot?
8.  Why should alpha be chosen using validation or cross-validation
    rather than simply selecting the smallest tree?

## Short answers

1.  Pre-pruning stops growth early; post-pruning grows first and cuts
    later.
2.  Alpha sets the cost of tree leaves.
3.  Many categories create many indicator columns, which can spread the
    data across weak splits.
4.  It has many candidate split points and can appear useful by chance.
5.  Shuffle one feature and measure how much the validation score drops.
6.  Predictive association can come from proxies, confounding, or
    leakage; it is not proof of causation.
7.  They describe node impurity, number of examples, class counts, and
    predicted class.
8.  The smallest tree may be too simple; cross-validation estimates
    which complexity generalises best.
