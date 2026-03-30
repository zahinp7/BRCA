# BRCA ER Status Classification

Machine learning pipeline for classifying breast cancer ER (Estrogen Receptor) status using multi-omics data from The Cancer Genome Atlas (TCGA-BRCA).

## Overview

This project builds and evaluates supervised classification models to predict ER status (Positive/Negative) from a high-dimensional multi-omics feature set including RNA-seq gene expression and reverse-phase protein array (RPPA) data. Four models are compared using cross-validation, ROC-AUC, and SHAP-based interpretability analysis.

## Results

| Model | CV Accuracy (5-fold) | ROC-AUC |
|---|---|---|
| Logistic Regression | 0.907 ± 0.018 | 0.919 |
| Random Forest | 0.927 ± 0.012 | 0.918 |
| XGBoost | 0.933 ± 0.016 | 0.918 |
| SVM | 0.914 ± 0.022 | 0.908 |

Best overall model: **XGBoost** (93.3% CV accuracy, ROC-AUC 0.918)

## Project Structure

```
BRCA/
├── scripts/           # Full analysis notebook
├── results/           # Figures: ROC curves, confusion matrices, SHAP plots, PCA
├── report/            # Final project report
└── data/              # Multi-omics feature matrix and ER status labels
```

## Methods

- **Dataset**: TCGA-BRCA multi-omics dataset (549 samples, 1937 features)
- **Preprocessing**: Median imputation, StandardScaler normalization, stratified 80/20 split
- **Dimensionality reduction**: PCA for visualization
- **Models**: Logistic Regression, Random Forest, XGBoost, SVM
- **Evaluation**: 5-fold stratified cross-validation, ROC-AUC, confusion matrices
- **Interpretability**: SHAP TreeExplainer for XGBoost feature importance analysis

## Tech Stack

Python · scikit-learn · XGBoost · SHAP · pandas · NumPy · matplotlib · seaborn

## Authors

Zahin Peerzade 
Carnegie Mellon University
