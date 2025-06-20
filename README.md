# Country Statistics Regression Model

This project explores a complete machine learning pipeline for predicting a target variable from a multi-feature dataset containing country-level indicators. Using a variety of regression techniques — from linear to regularised and polynomial models — the project emphasises proper preprocessing, feature scaling, outlier handling decisions, and model tuning for real-world deployment.

---

## Project Summary

- Goal: Predict a continuous target variable based on socio-economic and population features using regression techniques.
- Final Model: Polynomial Regression with Lasso Regularisation (alpha = 0.1)
- Best Performance:
  - MSE: 10.71  
  - R²: 0.87

---

## Technologies Used

- Language: Python  
- Libraries: Scikit-learn, Pandas, NumPy, Matplotlib, Seaborn  
- Modelling Techniques:  
  - Linear Regression (Multivariate)  
  - Ridge and Lasso Regularisation  
  - Polynomial Regression  
  - GridSearchCV for hyperparameter tuning  
- Data Splitting:
  - Holdout Method (80/20)
  - 5-Fold Cross-Validation

---

## Workflow Overview

### 1. Exploratory Data Analysis
- Scatterplots and correlation heatmaps used to identify linear relationships
- Detected skewed distributions and significant scale differences (e.g. Status vs Population)

### 2. Baseline Model
- Multivariate Linear Regression  
- MSE: 23.76 | R²: 0.71

### 3. Preprocessing
- MinMax Scaling: Addressed large magnitude differences across features  
- Yeo-Johnson Normalisation: Handled skewness and retained robustness to outliers  
- Outlier Handling: Chose not to remove outliers (approximately 1400+ rows) to preserve potential signal

### 4. Categorical Features
- Skipped one-hot encoding for 'Country' and 'Year' due to high cardinality
- Future directions include binning or embeddings to reduce dimensionality

### 5. Regularisation and Tuning
- Applied Ridge and Lasso to control complexity and reduce multicollinearity  
- Hyperparameter tuning performed via GridSearchCV (5-fold cross-validation)

### 6. Model Development Progression
| Model Type                        | MSE     | R²      |
|----------------------------------|---------|---------|
| Baseline Linear Regression       | 23.76   | 0.712   |
| After Yeo-Johnson Normalisation  | 18.23   | 0.779   |
| Ridge Regression                 | 18.43   | 0.777   |
| Lasso Regression                 | 18.61   | 0.775   |
| Polynomial Regression            | 10.98   | 0.867   |
| Ridge on Polynomial              | 10.47   | 0.873   |
| Lasso on Polynomial (Final)      | 10.71   | 0.870   |

---

## Final Model

Lasso-Regularised Polynomial Regression (alpha = 0.1) was selected for its ability to generalise well and capture non-linear relationships. Regularisation improved interpretability while cross-validation ensured robust performance across data splits.

---

## Limitations and Future Work

- Outliers: Future models may incorporate z-score filtering or IQR-based detection  
- Categorical Variables: Explore binning or embedding methods for high-cardinality variables  
- Feature Selection: Implement L1-based or tree-based techniques to reduce dimensionality  
- Data Volume: Access to larger datasets would improve generalisability and model confidence


---

## Related Links

- Portfolio: [www.sam-portfolio.tech](https://www.sam-portfolio.tech)  
- LinkedIn: [linkedin.com/in/sam-peterson-179b73217](https://linkedin.com/in/sam-peterson-179b73217)

---

Author: Samuel Peterson  
Master of Data Science, RMIT University  
