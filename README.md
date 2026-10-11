# Feature Engineering for Regression

A small, reproducible machine-learning project comparing a baseline model with polynomial/interactions features and a Yeo-Johnson transformation.

## Project contents
- `notebooks/feature_engineering.ipynb` — complete notebook: data inspection, baseline, feature engineering, evaluation, plots, and interpretation.
- `docs/impact_report.md` — report template and guidance for recording the measured results.
- `data/raw_dataset_info.txt` — dataset provenance and notes.
- `requirements.txt` — Python dependencies.

## Dataset
The project uses the diabetes regression dataset bundled with scikit-learn (`sklearn.datasets.load_diabetes`). It contains 442 rows, 10 numeric input features, and a quantitative target. The notebook does not need a separate dataset download.

Dataset reference: scikit-learn documentation, “Diabetes dataset”:
https://scikit-learn.org/stable/datasets/toy_dataset.html#diabetes-dataset

## Setup
Python 3.10 or newer is recommended.

### Windows (PowerShell)
```powershell
py -m venv .venv
.\.venv\Scripts\Activate.ps1
python -m pip install --upgrade pip
pip install -r requirements.txt
jupyter notebook
```

### macOS/Linux
```bash
python3 -m venv .venv
source .venv/bin/activate
python -m pip install --upgrade pip
pip install -r requirements.txt
jupyter notebook
```

Open `notebooks/feature_engineering.ipynb` and choose **Kernel → Restart & Run All**.

## How to complete the submission
1. Run every notebook cell from top to bottom.
2. Review the comparison table and plots produced in Section 5.
3. Fill in the actual MAE, RMSE, and R² values in `docs/impact_report.md`. Do not guess values.
4. Save the notebook with outputs, if your instructor requires visible outputs.
5. Commit the files to your repository.

## Evaluation notes
MAE and RMSE are error metrics (lower is better); R² is a goodness-of-fit metric (higher is better). All models use the same train/test split. This is a demonstration and should not be interpreted as a clinical prediction tool.
