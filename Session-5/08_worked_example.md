# 8. Worked Example --- One Gradient Descent Step

The file includes a hand-worked example with two data points:

`(x, y) = (1, 2)`

and

`(2, 3)`

The goal is to show what **one complete Gradient Descent step** looks
like.

## The general process

For the current parameters:

1.  calculate predictions
2.  calculate errors
3.  calculate the cost
4.  calculate the gradient
5.  multiply the gradient by the learning rate
6.  subtract that step from the parameters
7.  calculate the new cost

The important idea is not to memorize the numbers. The important idea is
the workflow.

## Why do we do this by hand?

Because it makes the update rule concrete.

Instead of thinking:

"Gradient Descent somehow changes the weights"

we can see:

"Here are the current weights → here is the error → here is the gradient
→ here is the update → the cost becomes smaller."

The example in the file shows the cost changing from approximately:

`J: 3.25 → 1.41`

after one step.

That means the step moved **downhill**.

## What happens after one step?

We repeat the same process.

After many iterations, the parameters approach the minimum.

For a convex linear-regression cost, Gradient Descent can converge to
the same optimal parameters as the normal equation, assuming appropriate
optimization settings.

## Exam mindset

When given a Gradient Descent numerical question, always write:

``` text
1. prediction
2. error
3. gradient
4. learning-rate × gradient
5. new parameter
6. new cost
```

Do not skip the sign in the update.

Remember:

`new parameter = old parameter - learning rate × gradient`
