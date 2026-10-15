# Homework 1

Everything is in `homework_1.ipynb`:

- Problems 1-3: written answers (Markdown with LaTeX).
- Problem 4: fits five scikit-learn regression models to the ALE dataset and tests their out-of-fold residuals for normality (`scipy.stats.normaltest`, Shapiro-Wilk, Q-Q plots).
- Problem 5: logistic and probit classifiers (Breast Cancer Wisconsin) and linear regression with squared error and Student-t losses (ALE), all trained by mini-batch SGD in PyTorch with autograd, each compared with a scikit-learn baseline.

`homework_1.pdf` is the executed notebook exported to PDF.

## Data

The ALE dataset (UCI Machine Learning Repository, id 844) is included as `data/mcs_ds_edited_iter_shuffled.csv`, so the notebook runs without network access. The Breast Cancer Wisconsin data ship with scikit-learn.

## How to run

Requires Python 3.10 or later. From this folder:

```bash
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
python -m ipykernel install --sys-prefix --name python3
jupyter nbconvert --to notebook --execute --inplace homework_1.ipynb
```

The last command runs every cell from a fresh kernel (about 30 seconds on a laptop) and writes the outputs back into the notebook. To rebuild the PDF (needs a LaTeX installation with `xelatex`):

```bash
jupyter nbconvert --to pdf homework_1.ipynb
```

To work interactively, run `jupyter lab homework_1.ipynb`.

Random seeds are fixed. The numbers in the PDF were produced with Python 3.12, numpy 2.5, scipy 1.18, scikit-learn 1.9 and torch 2.14; `requirements.txt` gives version ranges, so small numerical differences are possible with other versions. The recipe above assumes `python3` on your PATH is 3.10 or later.
