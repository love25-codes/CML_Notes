# 11. Practical Workflow and Interview Questions

## A simple Gradient Descent workflow

When implementing Gradient Descent:

### Step 1 --- Prepare the data

-   choose features
-   choose target
-   handle missing/problematic values
-   scale features when appropriate

### Step 2 --- Initialize parameters

Start with some initial values for `θ`.

### Step 3 --- Calculate predictions

For linear regression:

`ŷ = Xθ`

### Step 4 --- Calculate errors

`error = prediction - actual`

### Step 5 --- Calculate gradient

For linear regression:

`gradient = (1/m) Xᵀ(error)`

### Step 6 --- Update parameters

`θ = θ - α × gradient`

### Step 7 --- Record the loss

Store the cost so you can plot it.

### Step 8 --- Repeat

Continue until convergence or until the iteration limit is reached.

### Step 9 --- Inspect the loss curve

Use it to detect bad learning-rate choices or optimization problems.

------------------------------------------------------------------------

# Interview / Exam Questions

## 1. Why is there a minus sign in Gradient Descent?

Because the gradient points toward increasing cost. We want to move in
the opposite direction, toward lower cost.

## 2. What happens if the learning rate is too small?

Training is stable but very slow.

## 3. What happens if it is too large?

The algorithm can overshoot, oscillate, diverge, or produce `NaN`.

## 4. Batch vs SGD vs mini-batch?

-   Batch = all examples per update
-   SGD = one example per update
-   Mini-batch = small group per update

Mini-batch is usually the practical default.

## 5. Why does feature scaling help?

It makes the optimization landscape more balanced, reducing zig-zagging
and speeding convergence.

## 6. Why is convexity useful?

A convex cost surface has a single global minimum, making optimization
much easier to reason about.

## 7. What is the most important formula?

`θ := θ - α∇J(θ)`

## 8. What should you remember?

The file's final ideas can be compressed into:

-   **gradient = error × feature** (for the simple linear-regression
    intuition)
-   **scaling reshapes the loss surface**
-   **learning rate controls step size**
-   **mini-batch is the practical default**
-   **convex problems have a global minimum**
