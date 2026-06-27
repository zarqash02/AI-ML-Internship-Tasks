# AI & ML Internship Tasks

A collection of machine learning projects completed as part of an AI/ML internship. Each task is contained in its own folder as a Jupyter Notebook, covering core ML concepts including regression, classification, time-series forecasting, and data visualization.

---

## Repository Structure

```
AI-ML-Internship-Tasks/
├── data-visualization/
├── heart-disease-prediction/
├── house-price-prediction/
└── stock-price-prediction/
```

---

## Tasks Overview

### Task 1 — House Price Prediction
**Folder:** `house-price_prediction/`

Predicts median house prices using the **California Housing Dataset**. Implements and compares regression models with full preprocessing, feature scaling, and evaluation.

- **Dataset:** California Housing Dataset (scikit-learn)
- **Models:** Linear Regression, Random Forest Regressor
- **Evaluation Metrics:** MAE, RMSE, R²

---

### Task 2 — Heart Disease Prediction
**Folder:** `heart-disease-prediction/`

Binary classification task to predict the presence of heart disease based on clinical patient attributes using the **UCI Heart Disease Dataset**.

- **Dataset:** UCI Heart Disease Dataset (303 samples, 13 features)
- **Models:** Logistic Regression, Decision Tree / Random Forest
- **Evaluation Metrics:** Accuracy, Precision, Recall, F1-Score, Confusion Matrix

---

### Task 3 — Stock Price Prediction
**Folder:** `stock-price-prediction/`

Time-series forecasting of **Apple Inc. (AAPL)** stock prices using historical market data fetched via `yfinance`.

- **Dataset:** AAPL historical price data (via yfinance)
- **Models:** Linear Regression, Random Forest Regressor
- **Evaluation Metrics:** MAE, RMSE, R²

---

### Task 4 — Data Visualization
**Folder:** `data-visualization/`

Exploratory data analysis and visualization of a dataset using Python visualization libraries. Focuses on uncovering patterns, distributions, and relationships in the data.

- **Libraries:** Matplotlib, Seaborn, Pandas

---

## Tech Stack

| Tool | Purpose |
|------|---------|
| Python 3.x | Core language |
| Jupyter Notebook | Development environment |
| Pandas & NumPy | Data manipulation |
| Scikit-learn | ML models and evaluation |
| Matplotlib & Seaborn | Visualization |
| yfinance | Stock data retrieval |

---

## Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/zarqash02/AI-ML-Internship-Tasks.git
cd AI-ML-Internship-Tasks
```

### 2. Create and activate a virtual environment

```bash
python -m venv .venv

# Windows
.venv\Scripts\activate

# macOS/Linux
source .venv/bin/activate
```

### 3. Install dependencies

```bash
pip install pandas numpy scikit-learn matplotlib seaborn yfinance jupyter
```

### 4. Launch Jupyter Notebook

```bash
jupyter notebook
```

Then navigate to any task folder and open the `.ipynb` file.

---

## Author

**Zarqash**    
[GitHub](https://github.com/zarqash02)
