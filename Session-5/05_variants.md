# 5. Batch, Stochastic and Mini-Batch Gradient Descent

There are three common ways to decide how many training examples are
used for one parameter update.

## 1. Batch Gradient Descent

Batch GD uses **all training examples** for every update.

If there are `m` examples, one step uses all `m`.

### Advantages

-   stable gradient
-   smooth learning
-   deterministic updates for a fixed dataset

### Disadvantage

For a huge dataset, calculating the gradient over every example can be
slow.

### Think of it as

"Look at the whole class before deciding what to change."

------------------------------------------------------------------------

## 2. Stochastic Gradient Descent (SGD)

SGD uses **one training example at a time**.

After seeing one example:

1.  calculate its gradient
2.  update parameters
3.  move to the next example

### Advantages

-   very fast individual updates
-   useful for large datasets
-   the noise can sometimes help escape shallow poor regions

### Disadvantage

The path is noisy and the loss may bounce around.

### Think of it as

"Make a decision after every single student."

------------------------------------------------------------------------

## 3. Mini-Batch Gradient Descent

Mini-batch GD uses a small group of examples at a time.

The file gives a typical range of about:

`32–256`

This is the practical default in many ML workloads.

### Why is it popular?

It provides a balance:

-   more stable than SGD
-   faster per update than full batch GD
-   works well with vectorized hardware such as GPUs

### Think of it as

"Look at a small group of students, then make a decision."

## Comparison

  Method         Examples per update Main idea
  ------------ --------------------- ------------------------
  Batch GD                       all stable but can be slow
  SGD                              1 noisy but fast updates
  Mini-batch             small batch practical balance

## Important idea

Noise is not always bad.

The randomness in SGD can sometimes help the optimizer move out of
shallow or poor regions.

For practical ML, mini-batch Gradient Descent is usually the important
one to understand.
