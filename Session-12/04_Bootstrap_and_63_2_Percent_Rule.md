# 4. Bootstrap Sampling and the 63.2% Rule

## What does “with replacement” mean?
When sampling with replacement, after a row is selected, it is put back before the next draw. The same row can therefore be selected several times.

For a dataset containing `n` rows, a bootstrap sample usually makes `n` draws from those `n` rows.

## Why does a bootstrap sample contain about 63.2% unique rows?
For any particular row:
- The probability it is **not** selected in one draw is `1 − 1/n`.
- The probability it is never selected in `n` draws is `(1 − 1/n)^n`.
- For large `n`, this approaches `e⁻¹ ≈ 0.368`.

So about `36.8%` of the original rows are left out, and the fraction included at least once is:

\[
1-0.368=0.632
\]

That is approximately **63.2% unique rows** in each bootstrap sample.

## Example
A dataset has 1,000 rows. A bootstrap sample makes 1,000 draws, but because some rows repeat, it contains roughly 632 distinct original rows on average. Roughly 368 rows are not selected.

## Remember
The sample still contains 1,000 draws; 63.2% refers to the expected proportion of **distinct original rows**, not the number of draws.
