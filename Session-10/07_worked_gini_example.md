# 7. Worked Example: Choosing a Split with Gini

The session gives a parent node with 6 examples: 3 positive and 3 negative.

## Step 1: Calculate the parent Gini
Each class makes up half of the examples:

\[
Gini(parent)=1-(3/6)^2-(3/6)^2=0.50
\]

The parent is mixed, so its Gini is `0.50`.

## Step 2: Evaluate Split A
Split A creates:
- Left child: 3 positive, 0 negative.
- Right child: 0 positive, 3 negative.

Both children are pure, so each child has Gini `0`.

Weighted child Gini:

\[
(3/6)(0)+(3/6)(0)=0
\]

Gini reduction = `0.50 - 0 = 0.50`.

## Step 3: Evaluate Split B
Split B creates two children, each with 2 examples of one class and 1 of the other.

Each child's Gini is:

\[
1-(2/3)^2-(1/3)^2\approx0.44
\]

Weighted child Gini is also about `0.44`.

Gini reduction = `0.50 - 0.44 = 0.06`.

## Which split wins?
**Split A wins** because its impurity reduction (`0.50`) is greater than Split B's (`about 0.06`).

## Lesson
The algorithm is not magic: it repeatedly compares candidate splits and keeps the one that cleans up the class groups the most.
