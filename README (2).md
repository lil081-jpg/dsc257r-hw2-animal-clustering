# Homework 2 (Q2) — Hierarchical Clustering of Animals

Coursework for **UCSD DSC 257R (Unsupervised Learning)**, Fall 2026.
Solution to Problem 2 of Homework 2, submitted as a Jupyter notebook.

## What this assignment covers

Clustering the **Animals with Attributes** dataset
([AwA](https://cvml.ista.ac.at/AwA/)) — 50 animals, each described by
85 real-valued features (does it have a tail, is it slow, does it have
tusks, …):

1. **Ward hierarchical clustering** — load the 50 × 85 continuous feature
   matrix (`predicate-matrix-continuous.txt`) and animal names
   (`classes.txt`), cluster with `scipy.cluster.hierarchy.linkage`
   (Ward's method), and plot the dendrogram (orientation `'right'`,
   each leaf labeled with the animal name).
2. **Cut the hierarchy into k = 10 clusters** — recover Ward's
   10-clustering via `fcluster`, list the animals in each cluster, and
   compute its **k-means cost** (sum of squared distances to cluster
   centers).
3. **Compare against k-means** — run k-means 10 times (each run
   initialized with 10 centers chosen at random from the data), keep the
   best (lowest-cost) solution, and show its clusters and cost.

## Files

| File | Description |
|---|---|
| `DSC257R_HW2_Q2.ipynb` | Complete solution notebook — clustering, dendrogram, and k-means comparison (original submission) |

## Reproducing

The notebook reads the AwA data files (`predicate-matrix-continuous.txt`,
`classes.txt`) from the working directory — course materials, not included
here. With them in place, run all cells top to bottom.

Requires `numpy`, `scipy`, `scikit-learn`, and `matplotlib`.

## Notes

- Ward's method minimizes the same objective as the k-means cost function,
  so comparing Ward's 10-clustering cost against the best of 10 k-means
  runs is a direct quality check.
- Figure size is set explicitly (`figsize=(10, 15)`) so the 50-leaf
  dendrogram stays readable.
