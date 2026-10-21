# 8. Permutation Importance

## What is it?

Permutation importance asks: **How much worse does the trained model
perform if we scramble one feature?**

The basic process: 1. Measure the model's baseline score on validation
data. 2. Shuffle the values in one feature's column. 3. Measure the
score again. 4. The drop in score is that feature's permutation
importance.

If scrambling a feature makes the score much worse, the model relies on
that feature for its predictions.

## Why is it useful?

-   It is model-agnostic: it can be used with different kinds of models.
-   Using validation data helps measure usefulness for generalisation,
    not just fit on training data.
-   It avoids the same high-cardinality split-point bias that can affect
    MDI.

## Limitations

-   It takes extra computation because the model must be evaluated again
    after shuffling.
-   Correlated features can share credit: if one is shuffled, another
    correlated feature may still provide similar information.
-   It still does not establish causation.

## MDI vs. permutation importance

  -----------------------------------------------------------------------
  MDI                                 Permutation importance
  ----------------------------------- -----------------------------------
  Uses impurity reductions inside the Measures the drop in a chosen score
  fitted tree                         after shuffling

  Can favour features with many       Avoids that particular cardinality
  possible split points               bias

  Convenient and quick to obtain      Requires repeated scoring
  -----------------------------------------------------------------------

## Remember

When a feature such as `customer_id` ranks high under MDI, check
permutation importance on validation data. If its importance falls near
zero, the MDI ranking may have been misleading.
