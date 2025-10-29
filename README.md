# Time-Series Stock Price Prediction (Notebook)

A compact walkthrough of **time-series regression** for equities:
- Load multi-ticker price CSVs (EBAY, NVDA, YHOO, AAPL, etc.)
- Engineer simple features (rolling stats, percent change, outlier fixes)
- Train **Ridge** regression to predict **AAPL**
- Evaluate with **no-shuffle** train/test split and cross-validation
- Visualize predictions vs actuals

## What’s Inside
1) **Data loading**
   - `prices_ebay_yahoo.csv`, `all_prices.csv`, `prices_ebay_yahoo_nvidia.csv`, `prices_of_four.csv`
   - Optional: `X.csv`, `y.csv` (pre-built design matrix/target)
2) **Feature engineering**
   - `percent_change(series)` over rolling windows
   - `replace_outliers(...)` (simple clipping/substitution)
3) **Model & evaluation**
   - `sklearn.linear_model.Ridge`
   - `cross_val_score(Ridge(), X, y, cv=3)`
   - `train_test_split(..., shuffle=False)` + `r2_score`
4) **Visualization**
   - Matplotlib line plots, tick control with `FixedLocator`

## Getting Started
```bash
# (Recommended) create and activate a virtual environment
python -m venv .venv

# Windows
.venv\Scripts\activate

# macOS/Linux
source .venv/bin/activate

#Git clone
git clone https://github.com/Joe-Naz01/time_series_pred.git
cd time_series_pred

pip install -r requirements.txt
