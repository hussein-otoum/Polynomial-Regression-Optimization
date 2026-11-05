# Polynomial Regression: Optimization Algorithms Comparison

## Project overview
This project compares six optimization algorithms for polynomial regression on five real Kaggle datasets. All model, gradient, loss, and optimizer calculations are implemented from scratch with NumPy.

## Algorithms
1. Gradient Descent (GD)
2. Stochastic Gradient Descent (SGD)
3. Mini-Batch Gradient Descent
4. RMSprop
5. Adam
6. Momentum

## Datasets
| Dataset | Kaggle source | Input feature | Target |
|---|---|---|---|
| Salary | https://www.kaggle.com/datasets/iamsouravbanerjee/Salary_dataset | YearsExperience | Salary |
| Auto MPG | https://www.kaggle.com/datasets/uciml/autompg-dataset | horsepower | mpg |
| California Housing | https://www.kaggle.com/datasets/camnugent/california-housing-prices | median_income | median_house_value |
| Medical Insurance | https://www.kaggle.com/datasets/mirichoi0218/insurance | age | charges |
| Bike Sharing Demand | https://www.kaggle.com/competitions/bike-sharing-demand/data | temp | count |

Bike Sharing is a competition dataset and may require accepting the competition rules.

## Notebook workflow
1. Load five Kaggle CSV datasets.
2. Clean the selected numeric feature and target.
3. Explore data and visualize feature-target relationships.
4. Split each dataset into 80% train and 20% test.
5. Standardize features and targets using training statistics only.
6. Generate polynomial features (degree 3).
7. Train six optimizers implemented using NumPy.
8. Evaluate MSE, RMSE, MAE, R² and training time.
9. Compare convergence curves and predictions.
10. Export result CSV files.

## Run on Kaggle
1. Create a new Kaggle Notebook.
2. Add the five datasets listed above using **Add Input**.
3. Upload/import `notebooks/polynomial_regression_optimization.ipynb` or copy its cells into the Kaggle Notebook editor.
4. Run all cells.
5. Download the result CSV files from the Output panel.

The notebook searches recursively in `/kaggle/input` for the expected filenames. If a Kaggle dataset uses a different filename, update the relevant `filename` in the `DATASETS` dictionary.

## Run locally
Install dependencies:
```bash
pip install -r requirements.txt
```
The notebook expects the CSV files to be available in a directory searched by the loader. For local use, place them under a directory such as `data/` and update the search roots in `find_kaggle_file`.

## Important methodological notes
- This is **univariate polynomial regression**: one numeric input feature per dataset.
- The polynomial model and all six optimization algorithms are implemented from scratch with NumPy.
- Pandas is used for CSV loading and cleaning; Matplotlib is used for charts.
- RMSE values should be compared within each dataset because target units differ.
- The notebook caps datasets larger than 12,000 rows for consistent runtime. Adjust this in `load_dataset` if full data is required.
- The notebook does not claim a predetermined best optimizer. Conclusions are generated from the actual test results.

## Repository structure
```text
polynomial-regression-optimization/
├── notebooks/
│   └── polynomial_regression_optimization.ipynb
├── results/
├── README.md
└── requirements.txt
```
