# 2. Post-Pruning (Grow First, Cut Later)

## What is it?

Post-pruning means allowing a decision tree to grow first and then
removing branches that do not justify their complexity.

## Why use it?

Pre-pruning makes a decision too early. A split may not look useful
immediately, even though it could lead to valuable splits below it.
Post-pruning examines a more complete tree before deciding what to
remove.

## Simple example

Suppose a tree is predicting whether a customer stays with a company. A
branch might initially seem to offer little improvement, but its later
branches could separate loyal customers from customers who leave.
Stopping early could miss that pattern.

With post-pruning, the tree is grown first, and the weaker branches are
considered for removal afterward.

## Trade-off

-   **Benefit:** Less short-sighted than stopping at each step.
-   **Cost:** Building the full tree first can take more computation.

## Remember

**Post-pruning = grow first, then cut back.**
