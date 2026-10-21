# 3. Cost-Complexity Pruning (`ccp_alpha`)

## Main idea

Cost-complexity pruning balances two things: 1. How much error the tree
makes. 2. How complicated the tree is.

The lecture gives this objective:

\[ R\_`\alpha`{=tex}(T) = R(T) + `\alpha `{=tex}\|T\| \]

Where: - (R(T)) is the tree's error or risk. - (\|T\|) is the number of
leaves. - (`\alpha`{=tex}) is the penalty (the "price") for having
leaves.

## How does alpha work?

-   **Small `ccp_alpha`:** Complexity is penalised less, so more
    branches can remain.
-   **Large `ccp_alpha`:** Complexity is penalised more, so more
    branches are removed.
-   **Very large `ccp_alpha`:** The tree can collapse toward the root.

A subtree is worth keeping when the error reduction it provides is large
enough to justify the extra leaves.

## Connection to regularisation

The general idea is similar to other methods that trade fit for
simplicity: - Ridge penalises large coefficients. - Lasso penalises the
number/magnitude of coefficients through an L1 penalty. - Adjusted
R-squared accounts for the number of model parameters. - Cost-complexity
pruning penalises the number of tree leaves.

## Remember

`ccp_alpha` controls how strongly the tree is encouraged to stay simple.
It is not simply a maximum-depth setting.
