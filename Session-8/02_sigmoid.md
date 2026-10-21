# Session 8 --- The Sigmoid

## What is the sigmoid?

The **sigmoid function** converts any real number into a number between
0 and 1.

The formula is:

\[ `\sigma`{=tex}(z)=`\frac{1}{1+e^{-z}}`{=tex} \]

where:

\[ z=`\beta`{=tex}\^T x \]

Usually, with an intercept:

\[
z=`\beta`{=tex}\_0+`\beta`{=tex}\_1x_1+`\beta`{=tex}\_2x_2+`\cdots`{=tex}
\]

------------------------------------------------------------------------

## Why do we need it?

The linear equation can produce any value:

``` text
-100
-5
0
3
100
```

But probability must be between 0 and 1.

The sigmoid fixes this:

``` text
very negative z → probability near 0
z = 0           → probability 0.5
very positive z → probability near 1
```

Examples:

     z   Sigmoid(z) approximately
  ---- --------------------------
    -5                      0.007
    -2                      0.119
     0                      0.500
     2                      0.881
     5                      0.993

------------------------------------------------------------------------

## Important property

\[ `\sigma`{=tex}(0)=0.5 \]

This is very important for questions.

Also:

-   sigmoid never becomes less than 0
-   sigmoid never becomes greater than 1
-   very negative inputs approach 0
-   very positive inputs approach 1

The ends are called **saturation**.

------------------------------------------------------------------------

## What does z mean?

`z` is the raw score produced by the linear part of the model.

Example:

\[ z=-4+2x \]

If:

\[ x=3 \]

then:

\[ z=-4+2(3)=2 \]

Now apply sigmoid:

\[ `\sigma`{=tex}(2)=`\frac{1}{1+e^{-2}}`{=tex}`\approx0.88`{=tex} \]

So the model gives approximately an **88% probability of class 1**.

------------------------------------------------------------------------

## Why is it still called regression?

The model is still linear in the transformed quantity called
**log-odds**.

The sigmoid is what converts that linear score into a probability.

So logistic regression is not simply "drawing a curved line." Its core
linear relationship is hidden behind the sigmoid transformation.

------------------------------------------------------------------------

## Memory trick

Think:

> **Sigmoid = probability converter**

And remember:

``` text
z → sigmoid → probability
```

The most important value:

> **z = 0 → probability = 0.5**
