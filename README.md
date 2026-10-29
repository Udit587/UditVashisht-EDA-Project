# EDA Course Project — US Seat Belts Dataset (BCSE331L)

This repository contains the complete Exploratory Data Analysis (EDA) course project, **Module 2 to Module 7 (Phases 1, 2 and 3)**, built on the **US Seat Belts** dataset: a US state-level panel dataset (50 states + Washington DC, 1983–1997) covering traffic fatality rates, seat-belt usage, speed-limit and drinking-age laws, income, and enforcement type.

**Dataset source:** [`USSeatBelts.csv`](https://raw.githubusercontent.com/salemprakash/EDA/main/Data/USSeatBelts.csv)

**Project demonstration video:** [Watch the video](https://drive.google.com/file/d/1jYKOxfT6KyeCxOq9vDo-iNY-ZW5E_Re-/view?usp=sharing)

## Repository Structure

```
├── README.md
└── Phase1_EDA_USSeatBelts.ipynb   # Phases 1, 2 and 3 in a single notebook (updated in place each phase)
```

Every cell in the notebook is numbered (`[Cell 1]` to `[Cell 168]`) so it can be followed alongside the demonstration video.

## Phase 1 — Exploratory Data Analysis (5 marks)

1. Loading the dataset
2. Basic statistical analysis
3. Handling missing data (state-wise median imputation, with the reason for the missingness explained)
4. Data cleaning
5. Data transformation (binning, derived flags, standardization)
6. Univariate analysis (4 visualizations)
7. Bivariate analysis (4 visualizations)
8. Multivariate analysis (4 visualizations)

## Phase 2 — Statistical Analysis & Clustering (5 marks)

9. **1D statistical analysis** — full summary statistics for `income` (mean, median, min, max, range, variance, SD, IQR, skewness, kurtosis), frequency and relative-frequency tables for `enforce` with pie and bar charts, and a binned frequency table with histogram and outlier box plot
10. **2D statistical analysis** — contingency table of `enforce` × `speed65` with row/column percentages and a stacked bar plot, grouped mean/median/SD of `income` by `enforce`, side-by-side box and violin plots, and Pearson/Spearman correlation with a regression scatter plot
11. **3D / N-D statistical analysis** — two-categorical + one-numerical summary with a faceted box plot and grouped bar chart with error bars, a scatter plot coloured/shaped by `enforce` with per-category correlation matrices, a full correlation heatmap, and a pairs plot
12. **K-Means clustering** — numerical feature selection (556 complete rows), standardization, k = 2 baseline with cluster centers, WCSS for k = 1–10, elbow plot, and the final k = 3 model chosen from the elbow
13. **Hierarchical clustering** — Euclidean distance matrix, Ward's-method linkage, dendrogram, a 3-cluster cut, and cluster sizes

## Phase 3 — Module 6: PCA and Module 7: Simple Linear Regression

14. **Principal Component Analysis (PCA)** — covariance matrix, eigenvalues/eigenvectors, explained and cumulative variance, scree plot, loadings heatmap, component scores (verified against scikit-learn), PC1 vs PC2 plots coloured by the K-Means and Hierarchical clusters, and a biplot
15. **Simple Linear Regression (SLR)** — `fatalities` predicted from `income` (the strongest single correlate), 80/20 train-test split, fitted regression equation, t-test and 95% confidence interval for the slope, R², MSE, RMSE and MAE on train and test sets, fitted-line and actual-vs-predicted plots, and residual analysis (residuals vs fitted, histogram, Q-Q plot)

> **Note on data used:** Sections 12–14 (clustering and PCA) reload the raw dataset and drop rows with missing values (556 of 765 rows remain), instead of using the imputed data from Phase 1. This follows the clustering assessment's procedure and is explained in the notebook. Section 15 (SLR) uses the cleaned Phase 1 data (765 rows); `income` and `fatalities` had no missing values.

Each section includes short markdown explanations of *why* each step/decision was made, not just the code itself.

## Key Findings

- **Fatality rates fell steadily from 1983 to 1997**, and are lower where seat-belt usage is higher. They are lowest under `primary` enforcement and highest where there is no seat-belt law.
- **Income has the strongest link with fatality rate** (Pearson ≈ −0.70, Spearman ≈ −0.74, both p < 0.001).
- **K-Means (k = 3) and Hierarchical clustering agree:** a lower-risk group (recent, wealthier, higher seat-belt usage), a higher-risk group, and a small group of 21 very high-mileage state-years.
- **PCA:** PC1 explains 49.6% of the variance and acts as a safety/development axis; PC2 (17.1%) is mainly traffic volume (`miles`). Three components retain 81.1% of the variance.
- **SLR:** fatalities = 0.038096 − 9.17 × 10⁻⁷ × income. Each extra $1,000 of income goes with a fatality rate about 0.00092 lower. The slope is highly significant (t ≈ −25, p ≈ 1.5 × 10⁻⁹⁵), and income alone explains about 51% (train) and 45% (test) of the variation in fatality rate.

## How to run

The notebook loads the dataset directly from the raw GitHub URL, so it can be run top-to-bottom in Google Colab or Jupyter with no manual file upload required. All outputs and plots are already saved in the notebook, so it can also be read without running anything.

1. Open the notebook in Google Colab (`File → Open notebook → GitHub`, then select this repository), or use the "Open in Colab" badge at the top of the notebook.
2. Run all cells (`Runtime → Run all`).
3. Save a copy back to this GitHub repository (`File → Save a copy in GitHub`).

> Re-running with different library versions can shift the K-Means cluster sizes slightly (a different local optimum); the elbow shape and the small 21-observation cluster stay the same.
