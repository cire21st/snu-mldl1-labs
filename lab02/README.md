# Lab 02 — Regularization, Trees, Ensembles & Clustering

Code-along exercises covering regularized regression, tree-based classifiers, ensemble methods, hierarchical clustering, and dimensionality reduction.

[Open in Google Colab](https://colab.research.google.com/github/cire21st/snu-mldl1-labs/blob/main/lab02/MLDL_Lab2.ipynb) · [View notebook](MLDL_Lab2.ipynb) · [Python export](mldl_lab2.py)

## Contents

| Section | Implementation |
| --- | --- |
| Ridge and Lasso regression | Closed-form Ridge weights and gradient-based Lasso; MSE comparison with ordinary least squares |
| Decision tree | Entropy-based feature and threshold selection for Iris classification |
| Random forest | Bootstrap samples, random feature subsets, and majority voting across trees |
| AdaBoost | Weighted resampling, decision stumps, and weighted predictions for binary classification |
| Hierarchical clustering | Agglomerative merging of the closest points from different clusters |
| PCA | Covariance eigendecomposition, projection onto two components, and visualization |

The estimators and evaluation helpers are implemented with NumPy and Python. Scikit-learn is used to load Iris. Despite the original Lab 2 syllabus mentioning K-means, the uploaded code uses hierarchical clustering and does not include K-means.

## Datasets

| Dataset | Use | Source |
| --- | --- | --- |
| Advertising | Ordinary, Ridge, and Lasso regression on sales | [ISL](https://www.statlearning.com/s/Advertising.csv) |
| Iris | Tree and forest classification, hierarchical clustering, PCA | `sklearn.datasets.load_iris()` |
| Default | Binary classification with AdaBoost | [ISLR-Python dataset](https://raw.githubusercontent.com/arthurcavila/ISLR-Python/master/Default.csv) |

The CSV files are read directly from their URLs. Internet access is required; no manual download or Google Drive mount is needed.

## Run

### Google Colab

Open the Colab link above and execute the cells from top to bottom. The Drive mount and directory-change lines in the notebook are commented out.

### Local notebook

Create and activate a Python 3 virtual environment. From the repository root:

```bash
python -m pip install -r requirements.txt
jupyter notebook lab02/MLDL_Lab2.ipynb
```

Run the cells in order because later sections reuse helper functions and variable names.

### Python export

From the repository root:

```bash
python lab02/mldl_lab2.py
```

The script is a Colab export. Use the notebook for inline tables and plots; bare expressions do not display automatically in script mode. Plot windows may need to be closed before the script continues.

## Implementation Notes

- `np.random.seed(42)` is set near the start, making the randomized splits and model sampling reproducible for the same execution order and environment.
- The decision tree, random forest, AdaBoost, and PCA are educational implementations rather than scikit-learn estimators.
- The random forest and decision tree are both evaluated on a validation split, but the final test evaluation currently sets `final_model = dt` explicitly. It does not automatically choose the higher-scoring validation model.
- The AdaBoost implementation resamples according to example weights, then calculates an unweighted error rate on the full training set. Interpret its accuracy as an outcome of this exercise implementation rather than a reference AdaBoost result.
- The hierarchical clustering section uses pairwise Euclidean distance and merges the clusters containing the closest pair of points. Its labels are cluster identifiers, not Iris class predictions.

These notes describe the archived implementation. The code has not been changed as part of this documentation update, and the notebook has not been rerun in a clean environment.

[Back to the lab archive](../README.md)
