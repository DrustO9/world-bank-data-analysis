# wb-econ-forecast

ML regression pipeline for **World Bank GDP / economic-growth forecasting** — 15.7k+ macroeconomic
records, 104 features, 5 economies. Benchmarks 10 regression models on a held-out split and ranks
them on R² and RMSE.

## What it does

- Loads the World Bank economic-growth indicators (`economy_growth.csv`) from the Kaggle
  [`georgejdinicola/world-bank-indicators`](https://www.kaggle.com/datasets/georgejdinicola/world-bank-indicators) dataset.
- Builds a standardised feature matrix (`StandardScaler`) and a train/test split.
- Fits 10 regression models on the same split and tabulates RMSE + R² for each.
- Renders horizontal bar charts of both metrics for easy comparison.

## Why it's interesting

The benchmark is a clean apples-to-apples comparison of linear models (Linear, Ridge, Lasso,
ElasticNet), tree models (Decision Tree, Random Forest, Gradient Boosting, XGBoost), a
kernel method (SVR with RBF), and an instance-based method (KNN) on identical
preprocessed inputs. **SVR comes out on top** at R² ≈ 0.545, RMSE ≈ 2.31 — a useful reminder
that tree ensembles aren't always the answer for macro-economic regression with modest sample sizes.

## Tech stack

- **Python 3** (Kaggle's `kaggle/python` Docker image)
- **scikit-learn** — Linear / Ridge / Lasso / ElasticNet / Decision Tree / Random Forest /
  Gradient Boosting / SVR / KNN, plus `StandardScaler` and metrics
- **XGBoost** — `XGBRegressor`
- **pandas, NumPy** — data wrangling
- **matplotlib, seaborn** — visualisation

## How to run

The notebook is wired up for Kaggle's filesystem (`/kaggle/input/...`). To run elsewhere:

```bash
pip install pandas numpy scikit-learn xgboost matplotlib seaborn jupyter
```

Open `world-bank-data (1).ipynb`, point the `pd.read_csv(...)` call at your local copy of
`economy_growth.csv` (download it from the Kaggle dataset above), then `Run All`.

## Key results

| Model | R² | RMSE |
|---|---|---|
| **SVR (RBF)** | **0.545** | **2.31** |
| Other 9 models | < 0.545 | > 2.31 |

(See the bar charts at the end of the notebook for the full ranking.)

> 📷 *Charts: see notebook cells — RMSE & R² horizontal bars by model.*

## License

MIT (add a `LICENSE` file if you want this enforced).
