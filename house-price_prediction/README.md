# House Price Prediction — California Housing Dataset

A machine learning project that predicts California house prices using regression models. Built as part of a university Machine Learning assignment.

---

## Objective

Predict median house prices based on property and location features using Linear Regression and Gradient Boosting, then evaluate and compare both models.

---

## Dataset

**California Housing Dataset** — originally derived from the 1990 U.S. Census.

| Feature | Description |
|---|---|
| `longitude` / `latitude` | Geographic coordinates |
| `housing_median_age` | Median age of houses in the block |
| `total_rooms` | Total rooms in the block |
| `total_bedrooms` | Total bedrooms in the block |
| `population` | Block population |
| `households` | Number of households |
| `median_income` | Median household income (in tens of thousands) |
| `ocean_proximity` | Categorical — distance from the ocean |
| `median_house_value` | **Target variable** — median house price ($) |

---

## Workflow

### 1. Data Preprocessing
- Filled missing values in `total_bedrooms` with the column median
- Engineered three new features:
  - `rooms_per_household` = total_rooms / households
  - `bedrooms_per_room` = total_bedrooms / total_rooms
  - `population_per_household` = population / households
- Applied `StandardScaler` to numerical features
- Applied `OneHotEncoder` to the `ocean_proximity` categorical column

### 2. Exploratory Data Analysis
- Distribution plot of target variable (`median_house_value`)
- Correlation heatmap across all numerical features
- Box plot of house prices by `ocean_proximity` category
- Geographic scatter plot of prices across California

### 3. Models Trained
- **Linear Regression** — baseline model
- **Gradient Boosting Regressor** — `n_estimators=200`, `learning_rate=0.1`, `max_depth=4`

Both models were built using `sklearn` Pipelines with the same preprocessor for a fair comparison.

### 4. Evaluation Metrics

| Model | MAE | RMSE |
|---|---|---|
| Linear Regression | $50,889 | $72,669 |
| Gradient Boosting | $33,400 | $50,113 |

Gradient Boosting outperforms Linear Regression by ~34% on MAE and ~31% on RMSE.

### 5. Visualizations
- Predicted vs Actual price scatter plots for both models
- Residual plot for the Gradient Boosting model
- Feature importance bar chart

---

## Requirements

```
pandas
numpy
matplotlib
seaborn
scikit-learn>=1.4
```

Install all dependencies with:

```bash
pip install pandas numpy matplotlib seaborn scikit-learn
```

---

## How to Run

1. Clone the repository:
   ```bash
   git clone https://github.com/zarqash02/AI-ML-Internship-Tasks.git
   cd AI-ML-Internship-Tasks/house-price-prediction
   ```

2. Install dependencies:
   ```bash
   pip install pandas numpy matplotlib seaborn scikit-learn
   ```

3. Launch Jupyter Notebook:
   ```bash
   jupyter notebook house_price_prediction.ipynb
   ```

4. Run all cells top to bottom (`Kernel → Restart & Run All`).

---

## Key Findings

- `median_income` is the single strongest predictor of house prices
- Geographic features (`latitude`, `longitude`, `ocean_proximity`) are highly influential
- Engineered features like `rooms_per_household` and `bedrooms_per_room` improve model performance
- Prices are capped at $500K in this dataset, which introduces bias at the upper end and inflates RMSE

---

## Skills Demonstrated

- Regression modeling (Linear Regression, Gradient Boosting)
- Feature engineering and scaling
- Categorical encoding (One-Hot Encoding)
- sklearn Pipelines and ColumnTransformer
- Model evaluation (MAE, RMSE)
- Data visualization (Seaborn, Matplotlib)

---

## Author

**Zarqash**  