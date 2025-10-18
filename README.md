# DataVerse — 1st Place Project (Phase Shift 2025)

Certificate awarded to Parikshith Aithal in recognition of exceptional performance for securing 1st Place in the event Dataverse at the International Level Annual Technical Symposium, Phase Shift 2025 (B.M.S. College of Engineering) on 19–20 September 2025.

Repository: https://github.com/aithal007/DataVerse_1st-place.git

## Project overview

This project predicts the Carbon Footprint for buildings using tabular data. The analysis and modeling are in `dataverse-final-6.ipynb` (notebook). The notebook contains data loading, preprocessing, feature engineering, model training and evaluation.

## What I did — high-level

- Data source: `train.csv` (originally loaded from a Kaggle input path in the notebook).
- Exploratory data cleaning:
  - Dropped `id` column (not useful) and `City` (single value — Bangalore).
  - Checked for missing values and handled types.
- Feature engineering:
  - One-hot encoded categorical columns: `Area`, `Building_Type`, `Building_Status`, and `Maintenance_Priority`.
  - Converted `Construction_Year` into `Building_Age` (2024 - Construction_Year).
  - Parsed `Last_Inspection_Date` to extract `Inspection_Year`, `Inspection_Month`, and computed `Days_Since_Inspection`.
  - Dropped the original `Last_Inspection_Date` after feature extraction.
  - Converted boolean dummy columns to integers.
  - Standard scaled numeric columns (using `StandardScaler`) while leaving one-hot dummies unscaled.

## Models trained

I trained multiple regression models and compared performance (MSE, RMSE, R²):

- Linear Regression
- Ridge Regression (alpha=1.0)
- Lasso Regression (alpha=0.01)
- Random Forest Regressor (n_estimators=200)
- Gradient Boosting Regressor (n_estimators=200)
- XGBoost Regressor (n_estimators=200, learning_rate=0.1)

Training setup:

- Features / target split: target column `Carbon_Footprint`.
- Train/test split: 70% train, 30% test (random_state=42).

## Reproducibility / How to run locally

1. Install dependencies (recommended to use a virtualenv or conda environment):

```powershell
python -m venv .venv; .\.venv\Scripts\Activate.ps1
pip install -r requirements.txt
```

2. Open the notebook in Jupyter or VS Code and run `dataverse-final-6.ipynb`.

3. To create a GitHub repo and push (if you want me to push, I need your permission and credentials on this machine):

```powershell
cd "c:\Users\Lenovo\Documents\DataVerse"
git remote add origin https://github.com/aithal007/DataVerse_1st-place.git
git branch -M main
git push -u origin main
```

If the remote already exists or you prefer SSH:

```powershell
git remote add origin git@github.com:aithal007/DataVerse_1st-place.git
git push -u origin main
```

Notes on pushing:
- Pushing requires valid GitHub credentials on this machine (HTTPS credentials or SSH key).
- If you prefer, I can guide you through creating a personal access token (PAT) and using it for the push.

## Files in this workspace (top-level)

- `dataverse-final-6.ipynb` — analysis & modeling notebook (original work).
- `Parikshith Aithal_Dataverse.pdf` — certificate PDF.
- `README.md` — this file (added).
- `requirements.txt` — Python dependencies (added).

## Notes, assumptions and next steps

- Assumed the notebook's data path is relative to Kaggle; you may need to update the path to `train.csv` when running locally.
- I did not alter the notebook. If you want I can extract code into .py scripts, add a `src/` module, or prepare a Colab-ready copy.
- Next step I can take: initialize a local git repo and create an initial commit (I can do that now), then attempt to push to your GitHub remote if you authorize.

If you'd like me to push now, reply and confirm you want me to attempt the push from this machine (I will attempt to push to the URL you provided). If you'd rather push yourself, follow the commands above.

— Parikshith's Dataverse project
