# 🎓 BSc Thesis — Robust Variable Selection under Cellwise and Rowwise Contamination

**Author:** Ferran Llorca  
**Program:** BSc Econometrics & Operations Research  
**Institution:** University of Groningen  
**Date of Submission:** June 16, 2025  
**Final Grade:** 8/10  

---

## 📘 Overview

This repository accompanies my Bachelor’s thesis, which investigates **robust variable selection** methods for high-dimensional regression under **cellwise** and **rowwise** contamination.  
The repository currently hosts the final thesis PDF and will soon include fully documented simulation and analysis code.

> **Focus:** Evaluating Lasso-type robust estimators using extensive Monte Carlo experiments to assess their performance in the presence of structured outliers.

---

## 📄 Thesis Document

📎 [Download the Thesis PDF](https://github.com/FLLC/bsc-thesis-robust-lasso/blob/main/thesis/Bachelor%C2%B4s%20Thesis.pdf)

The thesis benchmarks **robust Lasso-type methods** in sparse linear regression settings affected by both **casewise (rowwise)** and **cellwise** contamination.  
Monte Carlo simulations are used to assess how these methods balance **robustness**, **variable selection accuracy**, and **predictive performance**.

---

## 🚧 Repository Status

| Component | Status | Description |
|------------|---------|-------------|
| Thesis PDF | ✅ Complete | Final version of the submitted and graded thesis |
| Code cleanup | 🔄 In progress | Scripts are being refactored, documented, and structured |
| Reproducibility guide | ⏳ Planned | Will include environment setup and simulation instructions |

> ⭐ **Watch or star** this repository to receive updates as reproducible code and documentation are added.

---

## 🔍 Research Summary

Modern datasets often contain **localised contamination**, where individual cells—not entire observations—are corrupted.  
Such contamination invalidates traditional robust methods that assume rowwise outliers.  
This thesis evaluates estimators that either:
1. **Model robustness directly**, or  
2. **Pre-clean the data matrix** before estimation.  

Performance is measured through **out-of-sample prediction error**, **feature selection quality**, and **robust bias metrics** under varying contamination structures.

---

## 🧪 Methods Compared

| Category | Method | Description |
|-----------|---------|-------------|
| Baseline | **Lasso** | Standard ℓ₁-regularized regression |
| Robust (Response) | **LAD-Lasso** | Robust to outliers in the response variable |
| Robust (Combined) | **Sparse LTS (SLTS)** | Trimming-based estimator with ℓ₁ penalty |
| Robust (Covariance) | **GR-ALasso** | Gaussian-rank covariance + adaptive Lasso |
| Preprocessing | **DDC → Lasso** | DetectDeviatingCells preprocessing before standard Lasso |

Evaluation metrics include **RMSPE**, **F1-score**, **TPR/FPR**, **robust bias**, and **MAD** under structured contamination.

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
