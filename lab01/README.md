# Lab 01 — Regression & Classification

Code-along exercises covering array operations, data exploration, regression, feature selection, and classification.

[Open in Google Colab](https://colab.research.google.com/github/cire21st/snu-mldl1-labs/blob/main/lab01/MLDL_Lab1.ipynb) · [View notebook](MLDL_Lab1.ipynb) · [Python export](mldl_lab1.py)

## Contents

| Section | Implementation |
| --- | --- |
| NumPy and Pandas | Array creation, reshaping, broadcasting, matrix operations, DataFrames, and CSV loading |
| Linear regression | Simple and multiple regression using the normal equation; custom train/test split, MSE, and R² |
| Feature selection | Exhaustive subset selection using R² or adjusted R²; forward stepwise selection using five-fold cross-validation |
| Logistic regression | Sigmoid predictions, gradient descent updates, and classification accuracy |
| Linear discriminant analysis | Class means, priors, and a simplified discriminant score using a shared scalar variance |

The models and metrics are implemented with NumPy and Python. Scikit-learn is used to load the Iris dataset. The uploaded code ends at LDA; it does not currently include Naive Bayes.

## Datasets

| Dataset | Use | Source |
| --- | --- | --- |
| Carseats | DataFrame exploration | [Rdatasets / ISLR](https://vincentarelbundock.github.io/Rdatasets/csv/ISLR/Carseats.csv) |
| Advertising | Predict sales from advertising expenditure | [ISL](https://www.statlearning.com/s/Advertising.csv) |
| Boston | Feature selection with `crim` as the target | [Rdatasets / MASS](https://vincentarelbundock.github.io/Rdatasets/csv/MASS/Boston.csv) |
| Default | Binary default classification | [ISLR datasets mirror](https://raw.githubusercontent.com/LukeMoraglia/ISLR_datasets/master/data/Default.csv) |
| Iris | Discriminant analysis | `sklearn.datasets.load_iris()` |

CSV files are read directly from their URLs, so no manual download is needed. Internet access is required. Google Drive mounting is commented out.

## Run

### Google Colab

Open the Colab link above and execute the cells from top to bottom. If an imported package is missing, install it in the runtime first.

### Local notebook

Create and activate a Python 3 virtual environment. From the repository root:

```bash
python -m pip install -r requirements.txt
jupyter notebook lab01/MLDL_Lab1.ipynb
```

Run the cells in order; later sections reuse and overwrite variables defined earlier.

### Python export

From the repository root:

```bash
python lab01/mldl_lab1.py
```

The script is a Colab export. Use the notebook for inline tables and plots; bare expressions such as `df.head()` do not display automatically in script mode. Plot windows may need to be closed before the script continues.

## Implementation Notes

- Train/test splits and cross-validation folds are randomized without a fixed seed in the current calls, so results may vary.
- Exhaustive subset selection fits every non-empty feature combination and can take longer than the other sections.
- Linear regression explicitly inverts `X.T @ X`, which assumes an invertible matrix.
- The logistic regression target is encoded as `-1/1`, while the implemented sigmoid gradient uses the `0/1` target convention. These should be aligned before interpreting its accuracy.
- Forward selection appends a candidate before checking whether it improves validation MSE, so the returned subset can include the final non-improving feature.
- The LDA example uses a simplified scalar-variance score and reports accuracy on the same Iris samples used to estimate its parameters, rather than on a held-out test set.

These notes describe the archived implementation. The code has not been changed as part of this documentation update, and the notebook has not been rerun in a clean environment.

[Back to the lab archive](../README.md)
