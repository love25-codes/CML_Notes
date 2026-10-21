# 1. Why Averaging Reduces Variance

## Main idea
A single decision tree can be unstable: small changes in the training data may produce a different tree. This is called **high variance**.

Instead of trusting one tree, build many trees and combine their predictions. Their individual quirks can cancel out, while patterns shared by the trees remain.

## Simple example
Imagine five people estimating the same object's weight. Their guesses are 48, 52, 50, 47, and 53 kg. The average is 50 kg, which is less affected by any one person's unusually high or low guess.

## The important condition: correlation
Averaging works best when the models make different errors. If every tree behaves almost identically, combining them does not help much.

For `B` independent models, each with variance `σ²`, the variance of their average is:

\[
\\mathrm{Var}(\\bar f)=\\frac{\\sigma^2}{B}
\]

So, as the number of independent models increases, the average becomes less variable.

## Remember
- Averaging mainly reduces **variance**.
- It does not automatically remove bias.
- The models should not all make the same mistakes.
