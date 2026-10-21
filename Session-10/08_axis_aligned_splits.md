# 8. Axis-Aligned Splits

## What does axis-aligned mean?
A decision tree usually splits using one feature at a time, such as:

- `age < 30?`
- `income < 50000?`

On a graph, each split is parallel to one of the axes. It does not directly draw an angled or diagonal boundary in one step.

## Why can this be a limitation?
Imagine the true pattern separates two classes with a diagonal line. A tree cannot represent that diagonal with one split. It approximates the diagonal using many small horizontal and vertical steps—a staircase-like boundary.

A linear model can represent a straight diagonal boundary more directly, depending on the data and model.

## Remember
**One split tests one feature against a threshold.** Many such splits can approximate complicated boundaries, but a diagonal may need many steps.
