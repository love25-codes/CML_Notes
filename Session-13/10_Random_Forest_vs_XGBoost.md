# 10. Random Forest vs. XGBoost

Both are ensemble methods that combine decision trees, but they build and combine them differently.

| Point | Random Forest | XGBoost |
|---|---|---|
| Main idea | Bagging | Gradient boosting |
| Tree training | Trees are largely independent and can be trained in parallel | Boosting rounds are sequential |
| Main strength | Strong baseline with relatively little tuning | Often excellent tabular accuracy when tuned well |
| More trees | Usually does not overfit simply because more trees are added, though other settings still matter | Can overfit if too many boosting rounds are used |
| Tuning effort | Usually lower | Usually higher |
| Use when | You need a quick, robust baseline | You want to improve the baseline and can tune carefully |

## Recommended workflow
1. Train a Random Forest baseline.
2. Evaluate it on validation data.
3. Try XGBoost if further gains are needed.
4. Tune the learning rate, depth, sampling, and regularization.
5. Use early stopping.

## Interview-style question
**Why do bagging and boosting often use different base learners?**

Bagging often starts with flexible, deep trees that have low bias but high variance; averaging helps reduce their variance. Boosting often starts with shallow, high-bias learners and adds them sequentially to improve the fit in small steps.
