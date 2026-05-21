# World Bank Data Analysis

Exploratory analysis of World Bank economic-growth indicators in a Kaggle Jupyter notebook.

- **Dataset:** [George J. DiNicola — World Bank Indicators](https://www.kaggle.com/datasets/georgejdinicola/world-bank-indicators) (uses `economy_growth.csv`)
- **Environment:** Kaggle (`kaggle/python` Docker image)
- **Tools:** pandas, NumPy

## Open the notebook

The single file is [`world-bank-data (1).ipynb`](world-bank-data%20(1).ipynb). You can:

- Open it on Kaggle (the dataset path `/kaggle/input/datasets/...` is already wired in), or
- Run it locally with Jupyter — but then point the `pd.read_csv` call to your local copy of `economy_growth.csv`.

```bash
pip install pandas numpy jupyter
jupyter notebook
```
