# 11. Bagging vs. Boosting

## Bagging
- Trains multiple models independently, often in parallel.
- Combines their predictions.
- Mainly targets variance.
- In this session, the main example is bagging deep decision trees.

## Boosting
The session previews boosting as the next topic: instead of building trees independently, models are built **in sequence**, with each new model trying to fix mistakes made by earlier models.

## Simple analogy
- **Bagging:** ask many people independently, then combine their answers.
- **Boosting:** ask one person, inspect their mistakes, then let the next person focus on improving those mistakes.

## Remember
Bagging attacks variance by averaging independent models. Boosting builds models sequentially to address earlier errors; the exact mechanics depend on the boosting algorithm.
