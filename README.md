# DX799S-O1-Data-Science-Capstone-Milestone-2-Notebooks

This repository contains the notebook evidence and final report for Milestone Two of the DX799S-O1 Data Science Capstone. The project analyzes the synthetic **Marketing and Product Performance** dataset (10,000 rows; 17 columns) to evaluate whether campaign, product, customer, and promotional attributes support reliable revenue prediction or meaningful marketing-performance profiles.

The central finding is intentionally conservative: across supervised and unsupervised methods, the available synthetic attributes provide limited evidence for reliable revenue prediction or actionable natural segmentation. The notebooks document the analysis, diagnostics, safeguards, and evidence behind that conclusion.

## Repository contents

| Week | File | Topic | Summary |
|---|---|---|---|
| 8 | `WEEK_8.ipynb` | K-nearest Neighbors and Distance Metrics | Tests whether campaign attributes can distinguish high- from lower-revenue campaigns. The notebook compares Euclidean, Manhattan, Minkowski, and cosine distance metrics with five-fold cross-validation, a held-out test set, baseline comparison, scaling checks, F1, ROC AUC, and a confusion matrix. Results are near chance, indicating limited KNN classification signal. |
| 9 | `WEEK_9.ipynb` | Gradient Boosting Regression | Tests whether campaign, product, customer, and promotional variables can predict continuous revenue. The notebook uses an untouched test set, five-fold cross-validation, regularization-oriented tuning, RMSE/MAE/R², a baseline comparison, learning curves, and cautious feature-importance analysis. The tuned model performs near the mean-revenue baseline, indicating limited generalizable predictive signal. |
| 10 | `WEEK_10.ipynb` | K-means Clustering and Silhouette Analysis | Examines whether non-identifier business attributes form distinct campaign profiles. The notebook includes EDA, feature scaling, one-hot encoding, K-means models for k = 2–8, elbow and silhouette diagnostics, PCA visualization, and profile summaries. The best silhouette score is low, so the resulting groups are interpreted as tentative descriptive partitions rather than actionable segments. |
| 11 | `WEEK_11.ipynb` | DBSCAN and Hierarchical Agglomerative Clustering | Applies DBSCAN, core/border/noise point classification, epsilon/MinPts sensitivity analysis, HAC linkage comparisons, and a dendrogram. The analysis shows that visible engagement clusters are strongly influenced by the discrete satisfaction scale and linkage choice; results are exploratory rather than validated customer segments. |

## Dataset

- **Source:** Shah, I. (n.d.). *Marketing and Product Performance Dataset* [Data set]. Kaggle. https://www.kaggle.com/datasets/imranalishahh/marketing-and-product-performance-dataset
- **File used:** `marketing_and_product_performance.csv`
- **Scope:** Synthetic marketing campaign, product, customer, and promotional observations.

## Reproducibility notes

- All notebooks use a fixed random state (`42`) for reproducible sampling and model splits.
- Identifier columns are excluded from modeling because they are unique record labels and would encourage memorization.
- Revenue is excluded from clustering inputs and used only for descriptive post-clustering comparisons.
- Figures were rendered at 300 DPI for legibility in the final report.

## Sources used for methods

- Scikit-learn Developers. (n.d.). *Scikit-learn documentation*. https://scikit-learn.org/stable/
- Boston University. (2026). *Module C Milestone Two Guidelines and Rubric; Weeks 8–11 course materials.*
