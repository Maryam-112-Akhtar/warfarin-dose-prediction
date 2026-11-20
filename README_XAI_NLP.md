# Explainable AI and NLP for Warfarin Dose Prediction

This README describes the XAI and NLP explanation notebook for the warfarin dose-prediction project.

This project compares regression models for predicting the recorded therapeutic weekly warfarin dose using the IWPC dataset. It also applies SHAP to explain model predictions and uses a template-based natural-language generation function to convert key SHAP results into simple English explanations.

## Project overview

The project includes:

- Data cleaning and preprocessing
- Clinical-only and clinical-genetic feature configurations
- Linear Regression, Ridge Regression, Lasso Regression, and Random Forest Regression
- Hyperparameter tuning using five-fold cross-validation on the training data
- Model evaluation using MAE, RMSE, R², and the percentage of predictions within 20% of the recorded dose
- Kernel SHAP explanations for the final clinical-genetic Ridge Regression model
- Template-based natural-language explanations generated from SHAP values

## Dataset

The IWPC dataset was obtained through PharmGKB:

https://www.pharmgkb.org/downloads/

The raw dataset is not redistributed in this repository. Place the downloaded `IWPS.csv` file in the same folder as the notebook before running the analysis.

## How to run

1. Install the required packages:

```bash
pip install -r requirements.txt
```

2. Place `IWPS.csv` in the project folder.

3. Open and run the notebook:

```bash
jupyter notebook WARFARIN_XAI_NLP_FINAL.ipynb
```

4. The generated SHAP plots, result tables, NLP explanations, and Word report will be saved in the `xai_results/` folder.

## Main result

Among the models evaluated on the held-out test set, Ridge Regression with clinical and genetic information achieved the lowest MAE:

- MAE: 8.467 mg/week
- RMSE: 11.622 mg/week
- R²: 0.448
- Predictions within 20% of the recorded dose: 45.12%

## Explainable AI

The final clinical-genetic Ridge Regression model was explained using Kernel SHAP. A random background sample of up to 30 training records and a random sample of up to 20 held-out test records were used. The SHAP approximation used 100 samples.

SHAP values describe the behaviour of the fitted model. They do not establish causation, clinical safety, or treatment suitability.

## Natural language generation

A rule-based template natural-language generation function converts selected SHAP contributions into short English sentences. It identifies the top five features by absolute SHAP contribution and describes positive, negative, and near-zero contributions.

This is not a trained language model. The generated text describes model behaviour and should not be interpreted as medical advice.

## Important note

This project is for educational and research purposes only. It should not be used to prescribe, change, or make decisions about a real patient’s warfarin treatment. Clinical decisions should be made by qualified healthcare professionals.