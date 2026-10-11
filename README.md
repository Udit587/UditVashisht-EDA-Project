# EDA Course Project — US Seat Belts Dataset (BCSE331L)

This repository contains all phases of the Exploratory Data Analysis (EDA) course project, built on the **US Seat Belts** dataset — a US state-level panel dataset (1983–1997) covering traffic fatality rates, seat-belt usage, speed-limit and drinking-age laws, income, and enforcement type.

**Dataset source:** [`USSeatBelts.csv`](https://raw.githubusercontent.com/salemprakash/EDA/main/Data/USSeatBelts.csv)

## Repository Structure

```
├── README.md
└── Phase1_EDA_USSeatBelts.ipynb   # Phase 1 + Phase 2 (single notebook, updated in place each phase)
```

## Phase 1 — Exploratory Data Analysis (5 marks)

1. Loading the dataset
2. Basic statistical analysis
3. Handling missing data (state-wise median imputation, with the reason for the missingness explained)
4. Data cleaning
5. Data transformation (binning, derived flags, standardization)
6. Univariate analysis (4 visualizations)
7. Bivariate analysis (4 visualizations)
8. Multivariate analysis (4 visualizations)

## Phase 2 — Statistical Analysis, Clustering & PCA (5 marks)

9. **1D statistical analysis** — full summary statistics for `income` (mean, median, min, max, range, variance, SD, IQR, skewness, kurtosis), frequency and relative-frequency tables for `enforce` with pie and bar charts, and a binned frequency table with histogram and outlier box plot
10. **2D statistical analysis** — contingency table of `enforce` × `speed65` with row/column percentages and a stacked bar plot, grouped mean/median/SD of `income` by `enforce`, side-by-side box and violin plots, and Pearson/Spearman correlation with a regression scatter plot
11. **3D / N-D statistical analysis** — two-categorical + one-numerical summary with a faceted box plot and grouped bar chart with error bars, a scatter plot coloured/shaped by `enforce` with per-category correlation matrices, a full correlation heatmap, and a pairs plot
12. **K-Means clustering** — numerical feature selection (556 complete rows), standardization, k = 2 baseline with cluster centers, WCSS for k = 1–10, elbow plot, and the final k = 3 model chosen from the elbow
13. **Hierarchical clustering** — Euclidean distance matrix, Ward's-method linkage, dendrogram, a 3-cluster cut, and cluster sizes
14. **Principal Component Analysis (PCA)** — covariance matrix, eigenvalues/eigenvectors, explained and cumulative variance, scree plot, loadings heatmap, component scores (verified against scikit-learn), PC1 vs PC2 plots coloured by the K-Means and Hierarchical clusters, and a biplot

> **Note:** Sections 12–14 reload the raw dataset and drop rows with missing values (556 of 765 rows remain), instead of using the imputed data from Phase 1. This follows the clustering assessment's procedure and is explained in the notebook.

Each section includes short markdown explanations of *why* each step/decision was made, not just the code itself.

### How to run

The notebook loads the dataset directly from the raw GitHub URL, so it can be run top-to-bottom in Google Colab or Jupyter with no manual file upload required.

1. Open the notebook in Google Colab (`File → Open notebook → GitHub`, then select this repository), or use the "Open in Colab" badge at the top of the notebook.
2. Run all cells (`Runtime → Run all`).
3. Save a copy back to this GitHub repository (`File → Save a copy in GitHub`).

## Future Phases

Phase 3 of the project will be added to this same repository/notebook once instructions are released.
