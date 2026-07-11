# Privacy-Preserving Machine Learning — Notebooks & Summary

This repository is a set of notebooks that implement the main ideas from the book *Privacy-Preserving Machine Learning* by J. Morris Chang, Di Zhuang, and G. Dumindu Samaraweera (Manning, 2023).

Each notebook takes one technique from the book, explains it and then applies it to a real public dataset. The goal is to show not just the theory but also how each method actually behaves on data, and how the privacy budget (epsilon) trades privacy against accuracy. All datasets are pulled automatically from Kaggle through the `kagglehub` library, so the notebooks can be run end to end without any manual downloads.

## Notebooks


- **`task-1-dp-mechanisms.ipynb`**
  The three core differential privacy mechanisms: the binary (randomized response) mechanism, the Laplace mechanism, and the exponential mechanism. Each one is built from scratch and applied to the column type that fits it (binary, numerical, and categorical) on the Titanic dataset.

- **`task-2-differential-privacy-methods.ipynb`**
  Differentially private machine learning models: naive Bayes, logistic regression, linear regression and k-means clustering. Uses the `diffprivlib` library on a lifestyle and health-risk dataset.

- **`task-3.1-randomized-response.ipynb`**
  Local differential privacy for a simple yes/no question, using the randomized response mechanism on a student GenAI-usage survey.

- **`task-3.2-direct-encoding-ldp.ipynb`**
  Local differential privacy for categorical answers with more than two options, using direct encoding with its encode, perturb, and estimate steps.

- **`task-3.3-histogram-encoding-ldp.ipynb`**
  Local differential privacy for numerical and continuous data, using histogram encoding with the SHE and THE estimation methods.

- **`task-4.1-data-sanitization.ipynb`**
  The four data sanitization operations used when publishing data: generalization, suppression, perturbation and anatomization, each mapped to the right columns of a medical dataset.

- **`task-4.2-anonymity.ipynb`**
  The three anonymity models built on one recursive-partitioning engine: k-anonymity, l-diversity and t-closeness.

- **`task-NEW-pydp_notebook.ipynb`**
  A practical comparison using **OpenMined's PyDP library**. Each simple question is answered twice, once without privacy (the true value) and once with differential privacy, to show the effect of the privacy budget.

## How the notebooks are organised

Every notebook follows the same simple flow:

1. a short markdown intro that explains the technique and the dataset
2. loading and a quick look at the data
3. the implementation of the method
4. results, with comments that explain what the output means.

## Requirements

The notebooks use Python with `pandas`, `numpy`, `scikit-learn`, `matplotlib`, and `seaborn`, plus a few privacy-specific libraries: `kagglehub` (for the datasets), `diffprivlib`, and `python-dp` (PyDP). Each notebook installs what it needs, so you can open any one of them on its own and run it from the top.
