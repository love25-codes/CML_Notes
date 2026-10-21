# 4. Majority Vote: A Worked KNN Example

KNN classification predicts the class that appears most often among the `k` nearest training points.

The lecture uses the new point **Q = (3, 4)** and these examples:

| Point | Coordinates | Class | Distance from Q |
|---|---|---|---:|
| A | (2, 4) | Red | 1.00 |
| B | (4, 4) | Red | 1.00 |
| C | (3, 2) | Blue | 2.00 |
| D | (6, 5) | Blue | 3.16 |
| E | (1, 1) | Blue | 3.61 |

## If k = 3
The three closest points are A, B, and C.
- Red votes: 2 (A and B)
- Blue votes: 1 (C)

**Prediction: Red**

## If k = 5
All five points vote.
- Red votes: 2
- Blue votes: 3

**Prediction: Blue**

## What does this teach us?
The data did not change. Only `k` changed, and the prediction changed too.

- A small `k` listens to very close examples. It can react strongly to noise or unusual points.
- A larger `k` considers more examples. It can be steadier, but may overlook local patterns.

## Main takeaway
Choosing `k` is an important part of defining how KNN behaves.
