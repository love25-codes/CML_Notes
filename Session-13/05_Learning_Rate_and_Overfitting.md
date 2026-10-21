# 5. Learning Rate, Number of Trees, and Overfitting

## Two important settings
- `learning_rate`: how strongly each new tree changes the model.
- `n_estimators`: how many boosting rounds / trees to add.

These settings interact.

## Small vs. large learning rate
- A **small** learning rate makes cautious updates. It often needs more trees.
- A **large** learning rate makes bigger updates. It may learn quickly but can overfit more easily.

The lecture recommends trying a low learning rate (around `0.05`) and allowing enough boosting rounds, with early stopping to decide when to stop.

## What does overfitting mean?
A model overfits when it learns details or noise specific to the training data instead of patterns that generalize to unseen data. Training performance may keep improving while validation performance stops improving or gets worse.

Boosting can overfit because every new tree focuses on the current errors, which eventually may include noise.

## Early stopping
1. Keep a separate validation set.
2. Check validation loss after each round.
3. If it does not improve for a chosen number of rounds, stop.
4. Keep the best iteration, not necessarily the final one.

**Important:** Setting `n_estimators=10000` does not mean the model must use all 10,000 trees if early stopping is configured. Training accuracy of 100% alone is not proof that a model will perform well on new data.
