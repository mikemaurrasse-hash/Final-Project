# Notebook Comment Pack — AIM460 Fairness Benchmark

Use these comment headers at the TOP of key code cells to improve readability and grading clarity.

## 1) Environment & Imports
# PURPOSE: Initialize environment and reproducibility
# - Set random seeds (numpy/torch/sklearn)
# - Import pandas, numpy, matplotlib, sklearn, fairlearn, transformers
# - Configure warnings/logging

## 2) Data Loading (ACS Income/Employment, COMPAS, CivilComments)
# PURPOSE: Load raw datasets and align schemas
# - Read sources; select features/target; cast types
# - Attach sensitive attributes for EVAL ONLY (masked during training)

## 3) Data Cleaning & Imputation
# PURPOSE: Handle missing values/outliers
# - Numeric: KNNImputer (k=5)
# - Categorical: mode imputation
# - Optional: winsorize extreme values

## 4) Feature Engineering
# PURPOSE: Encode and scale features
# - OneHotEncoder for categoricals; StandardScaler for numerics
# - ColumnTransformer for reproducible pipeline
# - Train/Validation/Test with fixed seeds

## 5) Baseline Models
# PURPOSE: Train baselines
# - Tabular: LogisticRegression / tree baseline
# - Text: DistilBERT fine-tuning (CivilComments)
# - Save validation scores for post-processing

## 6) Metrics (Utility + Fairness)
# PURPOSE: Compute metrics
# - Utility: Accuracy, AUROC, Macro-F1
# - Fairness: DPD; Equalized Odds (TPR/FPR/TNR gaps)
# - Sensitive feature: census-derived (tabular), identity_any (CivilComments)

## 7) Mitigations
# PURPOSE: Apply fairness interventions
# - Pre: DSAP-style reweighting
# - In: Equalized Odds reductions
# - Post: Threshold Optimization (group-specific thresholds)

## 8) Exports (Figures + CSV + Overleaf)
# PURPOSE: Persist artifacts
# - Save tradeoff plots per dataset
# - Save consolidated results_summary_all.csv
# - Package figures and paper files for Overleaf