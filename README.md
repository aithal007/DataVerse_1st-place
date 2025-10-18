# DataVerse — Project Summary

Project: Predict building Carbon Footprint and suggest interventions to reduce emissions.

What this repository contains
- `dataverse-final-6.ipynb` — analysis, preprocessing, modeling, evaluation, and explainability.
- `Parikshith Aithal_Dataverse.pdf` — certificate.

How I built the model (short)
1. Data cleaning & feature engineering
   - Removed irrelevant columns (`id`, constant `City`).
   - One-hot encoded categorical features and converted booleans to integers.
   - Created `Building_Age` and inspection-related features from `Last_Inspection_Date`.
   - Standard scaled numeric features (StandardScaler) while keeping dummies intact.

2. Models trained & compared
   - Tried Linear Regression, Ridge, Lasso, Random Forest, Gradient Boosting, and XGBoost.
   - Evaluated with MSE, RMSE, and R on a 70/30 train/test split and with 5-fold CV.

3. Ensembling & tuning
   - Built a StackingRegressor (base: Lasso, LinearRegression, Ridge; final: LinearRegression).
   - Tuned Lasso and Ridge alphas and final estimator options with GridSearchCV (5-fold).

4. Explainability & predictions
   - Used SHAP to inspect feature impacts on model outputs.
   - Preprocessed test data to match training features, applied the trained scaler, and used the tuned stacking model to produce predictions and `submission.csv`.

How to run (local)
1. Create a venv and install dependencies:

```powershell
python -m venv .venv; .\.venv\Scripts\Activate.ps1
pip install -r requirements.txt
```

2. Open `dataverse-final-6.ipynb` in Jupyter/VS Code and run cells (update data paths if needed).
