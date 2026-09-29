# SNU MLDL I — Lab Archive

Personal code-along archive from **Machine Learning & Deep Learning I (Spring 2026)**, taught by **Prof. Joonseok Lee** at the **Graduate School of Data Science, Seoul National University**.

The code was typed out by hand while following the lectures as a record of independent study.

## Course Resources

- [Course Website](https://viplab.snu.ac.kr/viplab/courses/mldl1_2026_1/index.html) — syllabus and course materials
- [YouTube Lectures](https://www.youtube.com/playlist?list=PL0E_1UqNACXCpyohL0_uMNaqr0QuXOMBi) — watch the lectures online

## Labs

| Lab | Topics | Archive status |
| --- | --- | --- |
| [01](lab01/) | NumPy and Pandas, linear regression, feature selection, logistic regression, LDA | Notebook and Python export uploaded |
| [02](lab02/) | Ridge and Lasso regression, decision trees, random forests, AdaBoost, hierarchical clustering, PCA | Notebook and Python export uploaded |
| [03](lab03/) | CNNs with PyTorch, data augmentation, learning rate scheduling | Code not yet uploaded |
| [04](lab04/) | Attention, Transformers, masked language modeling | Code not yet uploaded |

## Getting Started

See the [Lab 1 guide](lab01/README.md) and [Lab 2 guide](lab02/README.md) for notebook contents, datasets, and execution instructions.

For local use, create and activate a Python 3 virtual environment, then run from the repository root:

```bash
python -m pip install -r requirements.txt
jupyter notebook lab01/MLDL_Lab1.ipynb
# Or: jupyter notebook lab02/MLDL_Lab2.ipynb
```

An internet connection is required to load the CSV datasets. The dependency list covers the uploaded Labs 1 and 2; package versions have not been pinned or validated in a clean environment.

## Repository Structure

```text
snu-mldl1-labs/
├── README.md
├── .gitignore
├── requirements.txt
├── lab01/
│   ├── README.md
│   ├── MLDL_Lab1.ipynb
│   └── mldl_lab1.py
├── lab02/
│   ├── README.md
│   ├── MLDL_Lab2.ipynb
│   └── mldl_lab2.py
├── lab03/
│   └── README.md
└── lab04/
    └── README.md
```

## Acknowledgments

This is a personal study archive, not an official course repository. Original teaching materials and lab examples belong to their respective authors.
