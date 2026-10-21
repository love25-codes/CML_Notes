# 1. k-Nearest Neighbours (KNN): The Basic Idea

## What is KNN?
**k-Nearest Neighbours (KNN)** is a machine-learning algorithm that predicts the answer for a new data point by looking at the most similar examples it has already seen.

Imagine you want to predict whether a person will like a movie. You find a few people with similar movie tastes and check whether they liked it. KNN uses the same idea with data.

## What does “nearest” mean?
“Nearest” means closest according to a distance calculation. Each example is described using features, such as age, income, height, or preferences. KNN calculates the distance between the new example and stored examples.

## What does `k` mean?
`k` is the number of neighbours to consider.
- `k = 1`: use the single closest example.
- `k = 5`: use the five closest examples.
- A larger `k`: consider a wider group.

## How KNN makes a prediction
1. Keep the labelled training examples.
2. For a new example, calculate its distance from the training examples.
3. Sort examples from closest to farthest.
4. Select the `k` closest examples.
5. For **classification**, use the most common label (majority vote).
6. For **regression**, commonly average their numerical target values.

## Classification vs regression
- **Classification:** predict a category, such as Red/Blue or spam/not spam.
- **Regression:** predict a number, such as a house price.

## Main takeaway
KNN says: **“Look at the examples most like this one, then use their answers to make a prediction.”**
