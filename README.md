# 🎓 BSc Thesis – Robust Variable Selection under Cellwise & Rowwise Contamination

**Author:** Ferran Llorca  
**Program:** BSc Econometrics & Operations Research  
**Thesis date:** June 16, 2025

> This repository contains the final thesis PDF (graded **8/10**) and a staging area for the simulation & analysis code, which is currently being cleaned and documented.

---

## 📄 Thesis PDF

- `Bachelor EOR Thesis, Ferran Llorca Mataix (S4847113).pdf`

The thesis evaluates **Lasso-type** and **robust** methods for sparse, high-dimensional regression under **rowwise (casewise)** and **cellwise** contamination, using extensive **Monte Carlo** experiments. :contentReference[oaicite:0]{index=0}

---

## 🚧 Repository Status

- **Code cleanup:** in progress (will push well-documented scripts + reproducible runs).
- **What’s already here:** the final thesis PDF and this README.
- **What’s coming:** simulation scripts, plotting code, environment files, and a reproducibility guide.

> If you star or watch the repo, you’ll see updates as the code lands.

---

## 🔍 Problem in One Paragraph

Outliers distort variable selection and prediction, and in modern datasets they often appear **per cell** rather than by whole rows. This study benchmarks methods that either **model robustness directly** (e.g., SLTS, LAD-Lasso, GR-ALasso) or **pre-clean the design matrix** (DDC) before fitting Lasso, comparing **out-of-sample error** and **feature-selection quality** across contamination types and levels. :contentReference[oaicite:1]{index=1}

## 🧪 Methods Compared

- **Lasso** (baseline)  
- **LAD-Lasso** (robust to response outliers)  
- **Sparse LTS (SLTS)** (trimming + ℓ₁ penalty)  
- **GR-ALasso** (Gaussian-rank covariance + adaptive Lasso)  
- **DDC ➜ Lasso** (DetectDeviatingCells preprocessing, then Lasso)

All are assessed for **RMSPE**, **F1**, **TPR/FPR**, **robust bias**, and **MAD** under controlled contamination schemes. :contentReference[oaicite:6]{index=6}

---

## 🧰 Planned Repo Structure

```
.
├── README.md
├── thesis/
│   └── Bachelor EOR Thesis.pdf
├── code/                  # (coming) cleaned R code
│   ├── 00_env/            # renv lockfile / session info
│   ├── 01_sim/            # data-generating process & contamination
│   ├── 02_fit/            # model fitting (glmnet, quantreg, robustHD, etc.)
│   ├── 03_eval/           # metrics & tables
│   └── 04_figs/           # plotting scripts
└── data/                  # (coming) cached simulation outputs (.rds / .qs)
```

---


## 🏛️ Citation & License

© 2025 **Ferran Llorca** — *University of Groningen*  
Bachelor's Thesis, BSc Econometrics and Operations Research 
