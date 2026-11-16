# Homework 1 – Solutions (Machine Learning)

Solutions to Homework 1 (30 points, four tasks) using scikit-learn. Each task covers a
regression, classification, data-normalization, or dimensionality-reduction/clustering problem.

| Task | Points | Topic | Dataset |
|------|--------|-------|---------|
| 1 | 5 | Regression (Ridge, Lasso, alpha tuning) | Superconductivity (21,263 materials, 81 features, target `critical_temp`) |
| 2 | 10 | Multiclass & binary classification (logistic regression, random forest) | Drug consumption (quantified), 1,885 records |
| 3 | 5 | Data normalization | Linnerud (20 records, 3 features + 3 targets) |
| 4 | 10 | Dimensionality reduction (Kernel PCA) and clustering (K-means) | Olivetti faces (400 images, 40 people) |

## Repository layout

```
notebooks/
  Homework1_solution.ipynb        # Solution notebook (downloads UCI data if not found locally)
  Homework1_solution_3010.ipynb   # Alternative solution notebook (reads train.csv from the working directory)
data/
  superconductivity/
    train.csv                     # 81 material features + critical_temp (UCI, ID 464)
    unique_m.csv                  # Chemical formulas (not used by the solution)
requirements.txt
```

## Setup

```bash
python -m venv .venv
source .venv/bin/activate        # Windows: .venv\Scripts\activate
pip install -r requirements.txt
jupyter notebook notebooks/
```

Notes on running the notebooks:

- `Homework1_solution.ipynb` looks for its data next to the notebook and downloads the UCI
  files automatically if they are missing.
- `Homework1_solution_3010.ipynb` loads `train.csv` from the working directory. Run it from
  `data/superconductivity/`, or copy `train.csv` next to the notebook.
- Random seeds are fixed (`random_state=42`). Small datasets (Linnerud, Olivetti) can still
  give slightly different numbers across library versions.

## Data sources

- Superconductivity: UCI Machine Learning Repository, dataset 464 – <https://archive.ics.uci.edu/dataset/464/superconductivty+data>
- Drug consumption (quantified): UCI, dataset 373 – <https://archive.ics.uci.edu/dataset/373/drug+consumption+quantified>
- Linnerud and Olivetti faces: loaded through `sklearn.datasets`.
