# Car Price Prediction

## Overview

This project develops a machine learning model to predict used car prices based on vehicle characteristics. The task is framed as a supervised regression problem, aiming to accurately estimate a continuous target variable (price) using real-world, noisy data.

---

## Data & Challenges

The dataset contains ~19k observations with a mix of numerical and categorical features. Several data quality issues were identified:

* Missing/invalid values (e.g. `Levy`)
* Incorrect data types (`Mileage`, `Engine volume`, `Doors`)
* Extreme outliers (e.g. unrealistic prices and mileage)
* High-cardinality features (e.g. `Model`)

The target variable (`Price`) was highly right-skewed, requiring transformation.

---

## Data Cleaning

Key steps included:

* Removing unrealistic price values (very low and extreme outliers)
* Cleaning and converting `Mileage`, `Levy`, and `Doors` to numeric
* Standardizing inconsistent formats
* Dropping irrelevant features (e.g. `ID`)

---

## Feature Engineering (Key Contribution)

Feature engineering was a critical component of this project and led to significant performance improvements.

Main transformations:

* Log transformation of skewed variables (including target)
* Created meaningful features:

  * `Years_Since_Prod`
  * `New_Car` (Mileage = 0)
  * `Turbo` (from Engine info)
  * `No_Levy`
* Binarized categorical variables (`Leather Interior`, `Wheel`)
* Bucketed variables (`Engine Volume`, `Airbags`)
* Removed high-cardinality feature (`Model`) to reduce overfitting risk

---

## Models

The following models were evaluated:

* Linear Regression
* Lasso Regression
* KNN
* Random Forest
* XGBoost

---

## Results

Feature engineering significantly improved model performance across all models.

* Random Forest improved from **R² ≈ 0.72 → 0.81**
* Tree-based models outperformed linear models, indicating non-linear relationships in the data
* Hyperparameter tuning provided only marginal improvements

---

## Conclusion

The project demonstrates that careful data cleaning and feature engineering can substantially improve predictive performance, often more than model complexity alone. Tree-based models, particularly Random Forest, proved most effective for this problem.

---

## Tools

Python, Pandas, Scikit-learn, XGBoost, Seaborn
