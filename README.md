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
│   └── Bachelor EOR Thesis, Ferran Llorca Mataix (S4847113).pdf
├── code/                  # (coming) cleaned R code
│   ├── 00_env/            # renv lockfile / session info
│   ├── 01_sim/            # data-generating process & contamination
│   ├── 02_fit/            # model fitting (glmnet, quantreg, robustHD, etc.)
│   ├── 03_eval/           # metrics & tables
│   └── 04_figs/           # plotting scripts
└── data/                  # (coming) cached simulation outputs (.rds / .qs)
```

---

## 🔁 Reproducibility (to be added with code)

- **Language:** R (tested on R 4.x)  
- **Core packages:** `glmnet`, `quantreg`, `robustHD`, `cellWise`, plus helper utilities for GR-ALasso from referenced authors. :contentReference[oaicite:7]{index=7}  
- **Design:** \(n=100\), \(p=300\), \(s=10\) active predictors, AR(1) correlation with \(r=0.5\); contamination levels \(\varepsilon \in \{0, 0.05, 0.10, 0.15, 0.20\}\); outlier magnitude \(\gamma=6\); 200 MC replications per \(\varepsilon\). :contentReference[oaicite:8]{index=8}  
- **Tuning:** primarily cross-validation; SLTS using BIC per literature; GR-ALasso via rank-based covariance + adaptive weights. :contentReference[oaicite:9]{index=9}

A `reproduce.R` (coming) will:  
1) set seeds and restore the environment; 2) run simulations; 3) fit models; 4) compute metrics; 5) regenerate tables/figures.

---

## 📈 Selected Results You’ll Find in the Thesis

- Distribution of **RMSPE** across contamination for each method and regime (rowwise vs. cellwise). :contentReference[oaicite:10]{index=10}  
- **F1** vs. contamination plots showing GR-ALasso’s edge at low ε and DDC’s stability as ε rises. :contentReference[oaicite:11]{index=11}  
- A **summary table** at ε=0% and ε=10% comparing RMSPE, F1, TPR, FPR, RB, MAD. :contentReference[oaicite:12]{index=12}

---

## 🗺️ Roadmap

- [ ] Upload cleaned R scripts (simulation, fitting, metrics, plots)  
- [ ] Add `renv.lock` and session info for exact reproducibility  
- [ ] Publish a lightweight vignette (`README-figures.md`) with key plots  
- [ ] Provide a ready-to-run script for a **small demo** replication

---

## 📚 How to Cite

If you reference this work, please cite the thesis PDF in this repository:  
“**Robust Variable Selection in Sparse Regression: An Analysis of Cellwise and Rowwise Outlier Handling Methods**,” Bachelor’s Thesis, June 16, 2025. :contentReference[oaicite:13]{index=13}

---

## 🤝 Acknowledgements

This project builds on robust statistics and sparse modeling literature (e.g., Huber, Rousseeuw, Tibshirani, Zou) and recent cellwise-robust advances (DDC, GR-ALasso). Full references are in the thesis PDF. :contentReference[oaicite:14]{index=14}

---

## 📬 Contact

- **Ferran Llorca** — ferran.llorca@outlook.com  
- LinkedIn: https://www.linkedin.com/in/ferranllorca/

> Questions or ideas? Feel free to open an issue or start a discussion.
