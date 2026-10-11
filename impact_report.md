# Feature Engineering Impact Report

## 1. Objective
Compare a simple linear-regression baseline with (a) degree-2 polynomial and interaction features and (b) a Yeo-Johnson power transformation. Use held-out regression metrics to evaluate whether each technique helps.

## 2. Dataset
- **Name:** scikit-learn diabetes regression dataset
- **Source:** https://scikit-learn.org/stable/datasets/toy_dataset.html#diabetes-dataset
- **Rows/features:** 442 observations and 10 numeric input features
- **Target:** quantitative measure of disease progression
- **Split:** 80% train / 20% test, `random_state=42`
- **Missing data:** the notebook checks this; median imputation is included in the pipelines for robustness.

## 3. Methods
1. **Baseline:** median imputation, standard scaling, ordinary least squares linear regression.
2. **Polynomial and interactions:** degree-2 polynomial expansion, scaling, and Ridge regression (`alpha=10`) to reduce overfitting.
3. **Mathematical transformation:** Yeo-Johnson power transformation, scaling, and Ridge regression (`alpha=1`). Yeo-Johnson is selected because this dataset includes centered values that may be negative, making a direct logarithm unsuitable.

## 4. Results
Run the notebook and copy the values from its comparison table into this table. Leave no guessed results in the final submission.

| Model | MAE | RMSE | R² |
|---|---:|---:|---:|
| Baseline: scaled linear regression | Fill after running | Fill after running | Fill after running |
| Degree-2 polynomial + Ridge | Fill after running | Fill after running | Fill after running |
| Yeo-Johnson + Ridge | Fill after running | Fill after running | Fill after running |

## 5. Interpretation
- Lower MAE/RMSE means smaller prediction errors on the test set.
- Higher R² means the model explains more of the variation in the held-out target.
- Polynomial features can capture curved relationships and interactions but create more features and can overfit.
- Yeo-Johnson can make feature distributions more suitable for a linear model, but it does not guarantee better predictive performance.
- Compare the measured results. State which model performed best on this split and whether the differences are substantial.

**Conclusion (complete after running):** On this split, the model with the lowest RMSE was ____________________. Its RMSE was ______ and R² was ______. Compared with the baseline, feature engineering ____________________ (improved / did not materially improve / worsened) performance. Interpret this conclusion cautiously because only one held-out split is used.

## 6. Interpretability and limitations
The baseline has the simplest feature interpretation. Polynomial terms add squared effects and pairwise interactions, making coefficients less direct. Power transformations also change the scale of features. This experiment uses a single train/test split and modest model settings; cross-validation and training-only hyperparameter tuning would provide a more reliable estimate. The dataset is for demonstrating machine-learning methods, not clinical use.
