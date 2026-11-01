# Warfarin Dose Prediction Using IWPC Data

This repository contains the analysis notebook and final figures for
a comparison of clinical-only and clinical–genetic regression models
for therapeutic weekly warfarin dose prediction.

## Models
Linear Regression, Ridge Regression, Lasso Regression,
and Random Forest Regression.

## Analysis
The modelling dataset contained 5,528 records:
4,422 training records and 1,106 test records.

Ridge, Lasso, and Random Forest hyperparameters were selected using
five-fold cross-validation on the training data.
Linear Regression was fitted without grid-search tuning.

The original published IWPC dosing equations were not implemented.

## Files
- WARFRAIN.ipynb: analysis code and saved outputs.
- mae_comparison.png: final overall MAE comparison.
- rmse_comparison.png: final overall RMSE comparison.
- dose_group_comparison.png: final Ridge dose-group MAE comparison.

## Dataset
The IWPC dataset was obtained through PharmGKB, accessed on
3 September 2026. The raw dataset is not included.

To rerun the notebook, obtain the dataset from its official source,
subject to the applicable access and use terms.
Place IWPS.csv in the same working folder as the notebook.

## Environment
Python 3.11.9
scikit-learn 1.8.0
pandas 3.0.3
NumPy 2.4.4
Matplotlib 3.10.9

## Running the analysis
Open WARFRAIN.ipynb in Jupyter or VS Code, select the appropriate
Python environment, and run the cells in order from top to bottom.
The notebook currently saves final outputs to the location defined
by final_dir; adjust that output location if needed.

## Scope
These are retrospective prediction results.
The models are not intended for individual clinical dosing decisions.
