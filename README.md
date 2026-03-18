# ACT Score Regression

## Requirements

```bash
python -m pip install jupyter pandas numpy scikit-learn matplotlib seaborn jax jaxlib openpyxl
```

## Usage

```bash
jupyter notebook
```

Open either notebook:

```bash
jupyter notebook act_regression_single_run.ipynb
jupyter notebook act_regression_optimizer_convergence.ipynb
```

The notebook uses the default remote dataset URL:

- `https://raw.githubusercontent.com/brian-fischer/DATA-5100/main/EdGap_data.xlsx`

## Files

- `act_regression_single_run.ipynb`: single-run training/evaluation workflow
- `act_regression_optimizer_convergence.ipynb`: four-mode comparison + convergence plots
