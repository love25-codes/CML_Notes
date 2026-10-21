# 1. Decision Tree Basics

## What is a decision tree?
A **decision tree** is a machine-learning model that makes a prediction by asking a sequence of questions. It works like a flowchart.

For example, to decide whether to approve a loan:
1. Is the person's age above 30?
2. If yes, is their income above ₹50,000?
3. Follow the answers until you reach a final prediction.

The questions and their possible answers form branches. The final prediction is written at a leaf.

## Parts of a tree
- **Root:** the first question; the top of the tree.
- **Node:** a point where the tree asks a question or holds a decision.
- **Branch:** a path followed after an answer.
- **Leaf:** the endpoint that gives the prediction.
- **Depth:** how many levels of questions are followed from the root.
- **Pure node:** a node where all examples belong to the same class.

## Why are decision trees useful?
- **No feature scaling is usually needed:** a split compares a feature with a threshold, such as `age < 30`. Multiplying every age by 1,000 does not change the ordering.
- **They can model non-linear patterns:** a tree can create different rules in different parts of the data.
- **They can capture interactions:** for example, a rule can depend on both age and income.
- **They are interpretable:** you can follow a path from root to leaf and explain the prediction in words.

## Remember
A decision tree learns a set of if/else questions from data.
