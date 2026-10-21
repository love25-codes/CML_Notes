# 04 — Bias–Variance Decomposition Proof (Simple Version)

## 1. Why do we need the proof?

The goal is to show that prediction error can be separated into:

```text
noise + variance + bias²
```

The session uses a simple algebraic trick:

> Add and subtract a mean, expand the square, and let the cross-term disappear.

This is done twice.

## 2. Step 1 — Split off the noise

Start with:

\[
(y-f_S)^2
\]

Add and subtract `\bar y`:

\[
(y-f_S)^2
=
[(y-\bar y)+(\bar y-f_S)]^2
\]

Now use:

\[
(a+b)^2=a^2+2ab+b^2
\]

So:

\[
(y-f_S)^2
=
(y-\bar y)^2
+
2(y-\bar y)(\bar y-f_S)
+
(\bar y-f_S)^2
\]

## 3. Why does the cross-term disappear?

The important fact is:

\[
E_y[y-\bar y]=0
\]

Why?

Because `\bar y` is the mean/expected value of `y` given `x`.

The deviation from its own mean has expectation zero.

Therefore, after taking expectation, the cross-term disappears.

We are left with:

```text
noise + remaining squared term
```

## 4. Step 2 — Split the remaining term

Now consider:

\[
E_S[(\bar y-f_S)^2]
\]

Add and subtract the average fitted prediction:

\[
\bar f
\]

Conceptually:

\[
\bar y-f_S
=
(\bar y-\bar f)+(\bar f-f_S)
\]

Again, square and expand.

The cross-term disappears for the same mean-deviation reason.

What remains is:

\[
(\bar y-\bar f)^2
+
E_S[(\bar f-f_S)^2]
\]

These are:

```text
bias² + variance
```

## 5. Final result

Combining Step 1 and Step 2:

\[
\boxed{
Error = Noise + Variance + Bias^2
}
\]

## 6. What you actually need to remember for exams

You normally do not need to reproduce every algebraic line unless asked.

Remember the structure:

```text
(y - prediction)²
        ↓
split around the true expected value
        ↓
noise + remaining error
        ↓
split remaining error around average model
        ↓
noise + bias² + variance
```

### Key trick

> **Add and subtract a mean → expand → cross-term becomes zero.**
