# AAPL Stock Price Prediction

A machine learning project that predicts Apple Inc. (AAPL) closing stock prices using **Linear Regression** and **Random Forest** models trained on historical OHLCV data from Yahoo Finance.

---

## Overview

This notebook demonstrates a complete ML pipeline for stock price prediction — from data acquisition and feature engineering to model training, evaluation, and comparison. Two models are trained on identical features and evaluated against each other and a naive baseline.

---

## Results

| Metric | Naive Baseline | Linear Regression | Random Forest |
|--------|---------------|-------------------|---------------|
| MAE    | $1.57         | $1.37             | $6.93         |
| RMSE   | —             | $1.76             | $9.67         |
| R²     | 0.9617        | 0.9729            | 0.1825        |

**Linear Regression outperforms both the naive baseline and Random Forest.**

Random Forest underperforms because it cannot extrapolate beyond price ranges seen during training — a known limitation of tree-based models on trending time series data.

---

## Dataset

- **Source:** Yahoo Finance via `yfinance`
- **Ticker:** AAPL (Apple Inc.)
- **Period:** January 2020 – January 2024
- **Frequency:** Daily OHLCV (Open, High, Low, Close, Volume)

---

## Features

Raw OHLCV prices are not fed directly into the model. Instead, derived features are engineered to avoid feature dominance (where `Open` would simply proxy `Close`):

| Feature | Description |
|---------|-------------|
| `prev_close` | Previous day's closing price — price level anchor |
| `prev_high` | Previous day's high |
| `prev_low` | Previous day's low |
| `gap_pct` | Overnight gap as % — (Open − prev_close) / prev_close |
| `intraday_range` | Daily volatility — (High − Low) / Open |
| `volume_ratio` | Today's volume relative to 5-day average |
| `momentum_3d` | 3-day price momentum ratio |
| `ma_5` | 5-day moving average of close (lagged) |
| `ma_10` | 10-day moving average of close (lagged) |

All features use lagged values to ensure no future data leaks into the model.

---


## Requirements

```
yfinance
scikit-learn
pandas
numpy
matplotlib
```

Install all dependencies:

```bash
pip install yfinance scikit-learn pandas numpy matplotlib
```

---

## How to Run

1. Clone the repository
   ```bash
   git clone https://github.com/zarqash02/AI-ML-Internship-Tasks.git
   cd AI-ML-Internship-Tasks/stock-price-prediction
   ```

2. Install dependencies
   ```bash
   pip install yfinance scikit-learn pandas numpy matplotlib
   ```

3. Open the notebook
   ```bash
   jupyter notebook stock_price_prediction.ipynb
   ```

4. Run all cells in order (`Kernel → Restart & Run All`)

---

## Notebook Structure

| Section | Description |
|---------|-------------|
| 1. Import Libraries | All required packages |
| 2. Load Dataset | Download and flatten yfinance MultiIndex data |
| 3. Feature Engineering | Derive lagged and relative features |
| 4. Train / Test Split | 80/20 chronological split (`shuffle=False`) |
| 5. Feature Scaling | StandardScaler fit on train, applied to test |
| 6. Linear Regression | Train, predict, and evaluate |
| 7. Random Forest | Train, predict, evaluate, and plot feature importances |
| 8. Comparison | Side-by-side metric comparison of both models |
| 9. Conclusion | Analysis of results and model behaviour |

---

## Key Design Decisions

- **No data shuffling:** Time series order is preserved to prevent future leakage into training
- **Lagged features only:** All features reference past data — the model never sees today's `Open` to predict today's `Close`
- **Naive baseline comparison:** Both models are benchmarked against a "predict yesterday's close" baseline to confirm genuine predictive value
- **StandardScaler:** Applied to both models for consistency, even though Random Forest does not require it

---

## Technologies

- **Python 3.14**
- **yfinance** — stock data download
- **scikit-learn** — model training and evaluation
- **pandas / numpy** — data manipulation
- **matplotlib** — visualization
