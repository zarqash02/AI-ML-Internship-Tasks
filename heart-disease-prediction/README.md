# Heart Disease Prediction — Binary Classification

A machine learning project that predicts whether a patient is at risk of heart disease using the **UCI Heart Disease Dataset**. Built as part of a Machine Learning assignment covering binary classification, medical data analysis, and model evaluation.

---

## Project Overview

This notebook walks through the complete ML pipeline — from raw data cleaning to model evaluation and feature importance analysis — using two classification algorithms: **Logistic Regression** and **Decision Tree**.

The dataset contains clinical records from patients across four hospitals (Cleveland, Hungary, Switzerland, VA Long Beach). The goal is to predict the presence of heart disease based on 13 health features.



---

## Dataset

**Source:** [UCI Heart Disease Dataset on Kaggle](https://www.kaggle.com/datasets/redwankarimsony/heart-disease-data)

| Column | Description |
|--------|-------------|
| `age` | Age in years |
| `sex` | Sex (Male / Female) |
| `cp` | Chest pain type (typical angina, atypical angina, non-anginal, asymptomatic) |
| `trestbps` | Resting blood pressure (mmHg) |
| `chol` | Serum cholesterol (mg/dl) |
| `fbs` | Fasting blood sugar > 120 mg/dl |
| `restecg` | Resting ECG results |
| `thalch` | Maximum heart rate achieved |
| `exang` | Exercise-induced angina |
| `oldpeak` | ST depression induced by exercise |
| `slope` | Slope of the peak exercise ST segment |
| `ca` | Number of major vessels coloured by fluoroscopy |
| `thal` | Thalassemia type |
| `num` | **Target** — 0 = No disease, 1–4 = Disease (binarised to 0/1) |

> The dataset uses string values for several columns (`sex`, `cp`, `thal`, etc.) and `num` as the target column. The notebook handles all of this in the cleaning step.

---

## Notebook Workflow

1. **Import Libraries** — numpy, pandas, matplotlib, seaborn, scikit-learn
2. **Load & Inspect Data** — shape, dtypes, statistical summary
3. **Data Cleaning**
   - Rename columns (`thalch` → `thalach`, `num` → `target`)
   - Drop irrelevant columns (`id`, `dataset`)
   - Encode string categoricals to integers
   - Convert booleans to int
   - Impute missing values (median for numerical, mode for categorical)
   - Binarise target variable
4. **Exploratory Data Analysis (EDA)**
   - Class distribution (bar + pie chart)
   - Numerical feature distributions by target class
   - Categorical feature breakdowns
   - Correlation heatmap
5. **Preprocessing** — Stratified 80/20 train-test split, StandardScaler
6. **Model Training** — Logistic Regression + Decision Tree
7. **Evaluation** — Accuracy, Confusion Matrix, Classification Report, ROC-AUC Curve
8. **Feature Importance** — LR coefficients + DT Gini importances

---

## Results

| Model | Accuracy | ROC-AUC |
|-------|----------|---------|
| Logistic Regression | ~85% | ~0.91 |
| Decision Tree | ~80% | ~0.82 |

**Logistic Regression** outperforms the Decision Tree on this dataset — its linear decision boundary generalises better on structured clinical data.

### Most Influential Features

| Feature | Effect |
|---------|--------|
| `cp` (chest pain type) | Strong predictor — asymptomatic type raises risk |
| `thalach` (max heart rate) | Lower values associated with higher disease risk |
| `ca` (major vessels) | More blocked vessels = higher probability |
| `oldpeak` (ST depression) | Higher values indicate greater risk |
| `thal` (thalassemia) | Reversible defect is a strong positive indicator |
| `exang` (exercise angina) | Presence significantly raises risk |

---

## Setup & Usage

### 1. Clone the repository
```bash
git clone https://github.com/zarqash02/AI-ML-Internship-Tasks.git
cd AI-ML-Internship-Tasks/heart-disease-prediction
```

### 2. Install dependencies
```bash
pip install numpy pandas matplotlib seaborn scikit-learn jupyter
```

### 4. Run the notebook
```bash
jupyter notebook heart-disease-prediction.ipynb
```

---

## Dependencies

| Library | Version |
|---------|---------|
| Python | 3.8+ |
| numpy | ≥ 1.23 |
| pandas | ≥ 1.5 |
| matplotlib | ≥ 3.6 |
| seaborn | ≥ 0.12 |
| scikit-learn | ≥ 1.1 |
| jupyter | ≥ 1.0 |

---

## Skills Demonstrated

- Binary classification with scikit-learn
- Medical data understanding and preprocessing
- Handling mixed-type datasets (strings, booleans, floats)
- Model evaluation using ROC-AUC and confusion matrix
- Feature importance analysis (coefficients + Gini impurity)
- Exploratory Data Analysis with matplotlib and seaborn

---

## Disclaimer

This project is built for **academic and educational purposes only**. The model is not intended for real clinical diagnosis or medical decision-making.
