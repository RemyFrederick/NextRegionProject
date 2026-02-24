# Plan: ACT Score Regression (Default MLP Only)

## Summary
Replicate the workflow of `ACT_Regression_Example.ipynb` using the local `EdGap_data.xlsx`, including data cleaning, mode imputation, standardization, and a single neural network regression model. Evaluation uses MSE on an 80/20 train/test split. Only the default `MLPRegressor()` is used, and only MSE is reported (no plots or weight visualizations).

## 1. Environment & Dependencies
Goal: Match notebook imports and behavior for the default MLP model.

- Use `pandas`, `numpy`.
- Use `scikit-learn` for preprocessing, model, and metrics.
- CPU only.

## 2. Data Loading
Goal: Match notebook source but use local file.

- Load `EdGap_data.xlsx`.
- Read `NCESSCH School ID` as object (string-like).

## 3. Column Renaming
Goal: Normalize names to match notebook.

Rename:

- `NCESSCH School ID` -> `id`
- `CT Pct Adults with College Degree` -> `percent_college`
- `CT Unemployment Rate` -> `rate_unemployment`
- `CT Pct Childre In Married Couple Family` -> `percent_married`
- `CT Median Household Income` -> `median_income`
- `School ACT average (or equivalent if SAT score)` -> `average_act`
- `School Pct Free and Reduced Lunch` -> `percent_lunch`

## 4. Cleaning & Missing Data Handling
Goal: Replicate notebook logic.

- Set invalid values to NaN:
  - `average_act < 1` -> NaN
  - `percent_lunch < 0` -> NaN
- Compute mode of each predictor column (excluding `id` and `average_act`).
- Fill NaNs with mode values.
- Drop any remaining NaNs.

## 5. Feature/Target Definition
Goal: Match notebook predictors.

- Target `y`: `average_act`.
- Predictors `X`: all columns except `id` and `average_act`.

## 6. Train/Test Split
Goal: Match notebook.

- `train_test_split(X, y, test_size=0.2)` (no fixed `random_state`).
- No validation split.

## 7. Standardization
Goal: Match notebook preprocessing.

- Fit `StandardScaler` on `X_train`.
- Transform `X_train` and `X_test`.

## 8. Model (Default MLP Only)
Goal: Run only the default neural network model.

- Fit `MLPRegressor()` with defaults.
- Compute test MSE.
- Print MSE only (no plots).

## Test Cases / Validation Scenarios

- File loads successfully from local path.
- Columns renamed correctly.
- Invalid values set to NaN and filled by mode.
- `id` excluded from predictors.
- Train/test split is 80/20.
- MSE computed without errors.

## Assumptions & Defaults

- Use local file `EdGap_data.xlsx`.
- Use only default `MLPRegressor()`.
- Use MSE as primary metric.
- Keep `test_size=0.2` with no validation split.
- No plots or weight visualizations.
