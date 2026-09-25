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
3. Handling missing data
4. Data cleaning
5. Data transformation
6. Univariate analysis (4 visualizations)
7. Bivariate analysis (4 visualizations)
8. Multivariate analysis (4 visualizations)

## Phase 2 — Statistical Analysis & Clustering (5 marks)

9. 1D statistical analysis (mean, median, mode, variance, std dev, skewness, kurtosis, IQR)
10. 2D statistical analysis (covariance, Pearson/Spearman correlation, ANOVA, significance testing)
11. 3D statistical analysis (three-way grouped summaries, pivot tables, 3D scatter plot)
12. K-Means clustering (elbow method, silhouette analysis, PCA visualization, cluster profiling)
13. Hierarchical clustering (dendrogram, agglomerative clustering, comparison with K-Means)

Each section includes short markdown explanations of *why* each step/decision was made, not just the code itself.

### How to run

The notebook loads the dataset directly from the raw GitHub URL, so it can be run top-to-bottom in Google Colab or Jupyter with no manual file upload required.

1. Open the notebook in Google Colab (`File → Open notebook → GitHub`, then select this repository).
2. Run all cells (`Runtime → Run all`).
3. Save a copy back to this GitHub repository (`File → Save a copy in GitHub`).

## Future Phases

Phase 3 of the project will be added to this same repository/notebook once instructions are released.
