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

15-minute video outline: "Using Data-Driven Models to Reduce Building Carbon Footprint"
- 0:00–0:30 — Intro: problem statement, dataset, and goal.
- 0:30–2:00 — Key features & preprocessing decisions.
- 2:00–4:30 — Models tried and why (linear vs tree-based vs ensemble).
- 4:30–7:00 — Stacking approach and brief overview of tuning.
- 7:00–9:00 — Evaluation: metrics, CV, and learning-curve checks.
- 9:00–11:30 — Explainability: SHAP summary and an example prediction.
- 11:30–13:30 — From prediction to action: interventions (energy efficiency, certification, maintenance) and estimated impacts.
- 13:30–14:30 — Deployment ideas: running the notebook, dashboard integration, monitoring.
- 14:30–15:00 — Closing and next steps.

How to run (local)
1. Create a venv and install dependencies:

```powershell
python -m venv .venv; .\.venv\Scripts\Activate.ps1
pip install -r requirements.txt
```

2. Open `dataverse-final-6.ipynb` in Jupyter/VS Code and run cells (update data paths if needed).

Notes
- I can generate speaker notes and slides for the 15-minute video if you want.
