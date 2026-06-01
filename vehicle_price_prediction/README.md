#  Vehicle Price Prediction Using Machine Learning

##  Project Overview

This project focuses on predicting used vehicle prices using machine learning techniques. The goal is to help buyers, sellers, and dealerships estimate fair market value based on vehicle specifications such as make, model, year, mileage, fuel type, transmission, drivetrain, and engine characteristics.

The project includes comprehensive data cleaning, exploratory data analysis (EDA), outlier treatment, feature engineering, categorical encoding, dimensionality reduction experiments, and regression modeling.

---

##  Objectives

* Analyze factors influencing vehicle prices.
* Handle missing values and inconsistent records.
* Detect and treat outliers in price, mileage, and cylinder count.
* Build a machine learning model to predict vehicle prices.
* Evaluate the impact of dimensionality reduction (PCA) on model performance.

---

##  Dataset Features

The dataset contains vehicle-related attributes including:

* Make
* Model
* Year
* Engine
* Cylinders
* Fuel Type
* Mileage
* Transmission
* Body Type
* Drivetrain
* Number of Doors
* Exterior & Interior Color
* Vehicle Description
* Price (Target Variable)

---

##  Exploratory Data Analysis

Several visualizations were created to understand data distribution and relationships:

### Key Analyses Performed

* Vehicle price distribution
* Fuel type distribution
* Average vehicle price by manufacturer and year
* Price distribution across drivetrain categories
* Correlation heatmap of numerical features
* Boxplots for numerical feature outlier detection

### Major Insights

* Vehicle mileage negatively impacts price.
* Certain manufacturers consistently command higher resale values.
* Price distributions are highly skewed with several luxury-car outliers.
* Drivetrain type contributes significantly to vehicle valuation.

---

##  Data Preprocessing

### Missing Value Treatment

Missing values were handled using:

* Mean imputation for numerical features:

  * Price
  * Mileage

* Mode imputation for categorical features:

  * Engine
  * Cylinders
  * Fuel
  * Body
  * Transmission
  * Colors
  * Trim
  * Doors

* Empty string replacement for descriptions.

### Outlier Handling

#### Price

* IQR-based filtering
* Extreme price records removed

#### Cylinders

* Invalid cylinder values (0.0) removed

#### Mileage

* Winsorization applied to cap extreme values

---

##  Feature Engineering

Selected features used for modeling:

* Make
* Model
* Year
* Cylinders
* Fuel Type
* Mileage
* Transmission
* Body Type
* Drivetrain
* Doors

### Categorical Encoding

One-Hot Encoding was applied using:

```python
pd.get_dummies()
```

Encoded features included:

* Make
* Model
* Fuel
* Transmission
* Body
* Drivetrain
* Year
* Cylinders
* Doors

This increased feature dimensionality from 11 features to 232 engineered features.

---

##  Machine Learning Model

### Linear Regression

A Linear Regression model was trained using:

* 80% Training Data
* 20% Testing Data

### Evaluation Metrics

* R² Score
* Mean Absolute Error (MAE)

---

##  Results

### Baseline Linear Regression

| Metric   | Value   |
| -------- | ------- |
| R² Score | 0.83    |
| MAE      | 4965.38 |

### Interpretation

* The model explains approximately **83% of the variation in vehicle prices**.
* Average prediction error is approximately **$4,965**.
* Results indicate a strong baseline regression model for used vehicle valuation.

---

##  PCA Experiment

To reduce dimensionality caused by one-hot encoding, Principal Component Analysis (PCA) was applied.

### PCA Process

* Standardized all features
* Selected components retaining 95% variance
* Re-trained Linear Regression on PCA-transformed data

### Results After PCA

| Metric   | Value    |
| -------- | -------- |
| R² Score | -62.10   |
| MAE      | 34959.07 |

### Observation

PCA significantly degraded model performance.

Possible reasons:

* Important price-related information was lost during transformation.
* Linear Regression benefited from original feature interpretability.
* High-cardinality categorical features contained predictive information that PCA compressed inefficiently.

---

##  Final Conclusion

The original Linear Regression model outperformed the PCA-based model by a large margin.

### Best Model

Linear Regression (Without PCA)

**Performance:**

* R² Score: **0.83**
* MAE: **4965.38**

### Key Findings

* Vehicle make, model, year, mileage, drivetrain, and fuel type strongly influence price.
* Proper outlier treatment significantly improves model reliability.
* One-Hot Encoding effectively captures categorical vehicle characteristics.
* PCA is not beneficial for this dataset and modeling approach.
* Linear Regression provides a strong baseline for vehicle price estimation.

---

## Technologies Used

* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Scikit-learn

---

## Project Workflow

1. Data Loading
2. Data Cleaning
3. Missing Value Imputation
4. Exploratory Data Analysis
5. Outlier Treatment
6. Feature Engineering
7. One-Hot Encoding
8. Train-Test Split
9. Linear Regression Modeling
10. Performance Evaluation
11. PCA Experimentation
12. Final Model Comparison

---

## Future Improvements

* Random Forest Regressor
* XGBoost Regressor
* LightGBM Regressor
* Target Encoding for high-cardinality features
* Hyperparameter Optimization
* Feature Selection Techniques
* Model Deployment using Flask/FastAPI
* Interactive Price Prediction Dashboard
