# ❤️ Heart Disease Detection Using Machine Learning

## Overview

This project focuses on predicting the presence of heart disease using clinical and physiological patient data.

The objective is to develop a machine learning model capable of identifying patients at risk of heart disease based on medical attributes such as blood pressure, cholesterol levels, heart rate, ECG results, and exercise-induced symptoms.

The project includes data preprocessing, feature scaling, exploratory data analysis, outlier handling, feature transformation, and machine learning model development using LightGBM.

---

## Problem Statement

Cardiovascular diseases remain one of the leading causes of mortality worldwide.

Early detection can significantly improve treatment outcomes and reduce healthcare risks.

The goal of this project is to build a predictive model that accurately classifies whether a patient is likely to have heart disease.

---

## Dataset Description

The dataset contains patient health information collected from clinical examinations.

### Features

- Age
- Sex
- Chest Pain Type
- Resting Blood Pressure
- Cholesterol
- Fasting Blood Sugar
- Resting ECG Results
- Maximum Heart Rate
- Exercise Angina
- Oldpeak
- ST Slope

### Target Variable

| Value | Meaning |
|---------|---------|
| 0 | No Heart Disease |
| 1 | Heart Disease Present |

---

## Data Preprocessing

### Feature Scaling

The following numerical features were standardized using StandardScaler:

- Resting Blood Pressure
- Cholesterol
- Maximum Heart Rate
- Oldpeak

Scaling ensures that all variables contribute equally to model learning and prevents dominance by large-scale features.

---

## Exploratory Data Analysis

Comprehensive visual analysis was performed to understand feature distributions and relationships with heart disease occurrence.

### Distribution Analysis

Histograms were generated for all features with target-based color segmentation.

Key observations:

- Patients with heart disease often showed different maximum heart rate distributions.
- Cholesterol and blood pressure displayed varying patterns across target classes.
- Exercise-induced symptoms demonstrated strong predictive potential.

---

## Correlation Analysis

A correlation heatmap was generated to examine relationships among features.

Important findings:

- ST Slope showed strong association with heart disease.
- Oldpeak exhibited significant predictive relevance.
- Maximum heart rate displayed inverse relationships with disease occurrence.

---

## Outlier Analysis

### IQR-Based Detection

Outliers were identified in the Resting Blood Pressure feature using the Interquartile Range (IQR) method.

#### Calculations

- First Quartile (Q1)
- Third Quartile (Q3)
- Interquartile Range (IQR)
- Lower Bound
- Upper Bound

Boxplots were used to visualize extreme observations.

---

## Outlier Handling

Two approaches were explored:

### 1. Winsorization (Capping)

Extreme values were capped at the calculated IQR boundaries.

Benefits:

- Preserves all observations
- Reduces influence of extreme values

### 2. Power Transformation

Yeo-Johnson Power Transformation was applied to:

- Resting Blood Pressure
- Cholesterol
- Oldpeak

Benefits:

- Reduces skewness
- Produces more Gaussian-like distributions
- Improves model performance

---

## Final Modeling Dataset

The transformed dataset was selected for model development because it provided improved feature distributions and reduced the impact of outliers.

---

## Machine Learning Model

### LightGBM Classifier

A Light Gradient Boosting Machine (LightGBM) model was trained to classify heart disease occurrence.

LightGBM was selected because:

- High predictive performance
- Fast training speed
- Ability to handle complex feature interactions
- Robustness against overfitting

---

## Model Training

### Train-Test Split

- Training Data: 80%
- Testing Data: 20%

### Algorithm

```python
LightGBM Classifier

---

## Evaluation Metrics

The LightGBM model was evaluated using multiple classification metrics to assess its predictive performance:

- Accuracy Score
- Precision Score
- Confusion Matrix
- Classification Report

Additional insights were obtained through:

- Class-wise Precision
- Class-wise Recall
- F1-Score

---

## Results

The LightGBM classifier demonstrated strong predictive performance in identifying patients with heart disease.

Key observations:

- High overall classification accuracy
- Balanced precision and recall across classes
- Effective identification of heart disease cases
- Reduced false-negative predictions, which is particularly important in healthcare applications

These results indicate that the model has potential as a decision-support tool for early cardiovascular risk assessment.

---

## Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-Learn
- LightGBM

---

## Key Learnings

- Medical datasets require careful preprocessing and outlier treatment.
- Feature transformation can significantly improve data distribution and model performance.
- LightGBM is highly effective for structured healthcare datasets.
- Exploratory Data Analysis helps identify clinically relevant predictors before model development.

---

## Future Improvements

- Hyperparameter Optimization using GridSearchCV
- SHAP-Based Explainability Analysis
- Feature Importance Interpretation
- Ensemble Learning Approaches
- Deployment as a Clinical Decision Support Application

---

## Author

**Chaitali Jadhav**

Data Analytics | Machine Learning | Healthcare AI | Deep Learning
