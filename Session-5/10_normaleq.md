
# 10. Normal Equation vs Gradient Descent

## Two ways to find model parameters

For linear regression, there are two important approaches:

1.  Normal Equation / closed-form solution
2.  Gradient Descent

## Normal Equation

The normal equation directly computes the optimal parameters.

The advantage is that you do not need to choose a learning rate or run
many iterations.

But the closed-form approach can become expensive with many features
because matrix operations such as matrix inversion can be costly.

The file notes a cost on the order of:

`O(p³)`

for the relevant closed-form operation, where `p` relates to the number
of parameters/features.

It can also run into problems with singular matrices.

## Gradient Descent

Gradient Descent takes an iterative approach.

Instead of calculating the answer directly:

``` text
start somewhere
↓
calculate gradient
↓
take a step
↓
repeat
↓
converge
```

## Important result

For the linear-regression example, batch Gradient Descent can converge
to the **same parameters** as the normal equation.

So they are different roads to the same minimum.

## Why is Gradient Descent more general?

The file emphasizes that the closed-form solution does not exist for
every model.

For logistic regression, for example, there is no equivalent simple
normal-equation solution.

Gradient-based optimization gives us a more general strategy for
differentiable cost functions.

## Easy comparison

  Normal Equation                                    Gradient Descent
  -------------------------------------------------- ---------------------------
  Direct calculation                                 Iterative
  No learning rate                                   Needs learning rate
  Convenient for smaller problems                    Useful for large problems
  Matrix computation can be expensive                Can use mini-batches
  Specific to problems with a suitable closed form   Much more general

## Main takeaway

Do not think of Gradient Descent as "a trick for linear regression."

Think of it as a general optimization idea that appears again and again
in machine learning.
