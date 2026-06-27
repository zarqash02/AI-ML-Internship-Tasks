# Iris Dataset — Data Visualization

An exploratory data analysis (EDA) notebook that visualizes the classic Iris dataset using Python's Seaborn and Matplotlib libraries.

---

## Overview

This notebook performs a structured visual exploration of the Iris dataset, covering basic data inspection, feature distributions, and species-level comparisons through scatter plots, histograms, and box plots.

---

## Dataset

**Iris Dataset** — loaded directly via `seaborn.load_dataset("iris")`

- 150 samples across 3 species: *Setosa*, *Versicolor*, and *Virginica*
- 4 numerical features: `sepal_length`, `sepal_width`, `petal_length`, `petal_width`
- 50 samples per species (balanced)

---

## Notebook Structure

| Step | Description |
|------|-------------|
| 1. Import Libraries | Load Seaborn and Matplotlib |
| 2. Load Dataset | Fetch the Iris dataset via Seaborn |
| 3. Data Inspection | Check columns, shape, dtypes, head, and descriptive statistics |
| 4. Class Distribution | Count samples per species |
| 5. Scatter Plot | Sepal Length vs. Sepal Width, color-coded by species |
| 6. Histograms | Distribution of all four numerical features |
| 7. Box Plot | Feature spread and outlier detection across all columns |
| 8. Conclusion | Key takeaways from the analysis |

---

## Visualizations

**Scatter Plot** — Sepal Length vs. Sepal Width by Species  
Shows how species cluster differently in sepal dimensions.

**Histograms** — Distribution of All Features  
Reveals the shape and spread of each numerical feature.

**Box Plot** — Iris Feature Spread  
Highlights median, interquartile range, and potential outliers per feature.

---

## Key Findings

- Petal length and petal width are the strongest visual separators between species.
- *Setosa* is linearly separable from the other two species based on petal dimensions.
- Sepal features show more overlap, especially between *Versicolor* and *Virginica*.
- Box plots indicate some outliers in sepal width.

---

## Requirements

```bash
pip install seaborn matplotlib
```

| Library | Purpose |
|---------|---------|
| `seaborn` | Dataset loading and statistical plots |
| `matplotlib` | Plot rendering and customization |

---

## Usage

```bash
git clone https://github.com/zarqash02/AI-ML-Internship-Tasks.git
cd AI-ML-Internship-Tasks/data-visualization
jupyter notebook data-visualization.ipynb
```

---

## License

This project is open source and available under the [MIT License](LICENSE).
