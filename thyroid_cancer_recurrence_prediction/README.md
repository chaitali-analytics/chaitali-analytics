# Thyroid Cancer Recurrence Prediction using Machine Learning

## Project Overview

This project focuses on predicting thyroid cancer recurrence using clinical and pathological patient information. The objective is to identify patients who are at a higher risk of recurrence after treatment, enabling improved monitoring and personalized clinical decision-making.

The project includes data preprocessing, categorical feature encoding, exploratory data analysis, correlation analysis, feature engineering, and classification using Logistic Regression.

---

## Problem Statement

Thyroid cancer generally has a favorable prognosis, but recurrence remains a significant clinical concern for some patients.

The goal of this project is to develop a machine learning model capable of predicting whether a patient is likely to experience cancer recurrence based on demographic, clinical, pathological, and treatment-related factors.

---

## Dataset Features

The dataset contains patient information including:

### Demographic Features

- Age
- Gender

### Clinical Features

- Thyroid Function
- Physical Examination Findings
- Adenopathy

### Pathological Features

- Pathology Type
- Focality
- Risk Category

### Cancer Staging Features

- T Stage
- N Stage
- M Stage
- Overall Stage

### Treatment Response Features

- Response to Treatment
- Smoking History
- Radiotherapy History

### Target Variable

- Recurred

Classes:

- 0 → No Recurrence
- 1 → Recurrence

---

## Data Preprocessing

### Binary Encoding

The following binary categorical variables were converted into numerical format:

- Smoking
- Hx Smoking
- Hx Radiotherapy
- Recurred

Encoding:

- No → 0
- Yes → 1

---

### Gender Encoding

Gender was encoded as:

- Male → 0
- Female → 1

---

### One-Hot Encoding

The following categorical variables were transformed using One-Hot Encoding:

- Thyroid Function
- Physical Examination
- Adenopathy
- Pathology
- Focality
- Risk
- T Stage
- N Stage
- M Stage
- Overall Stage
- Response

This conversion allowed machine learning algorithms to process categorical information effectively.

---

## Exploratory Data Analysis

Several visualization techniques were used to understand the dataset and identify relationships with recurrence.

### Analyses Performed

- Age Distribution Analysis
- Gender Distribution
- Recurrence Distribution
- Feature-wise Recurrence Comparison
- Correlation Analysis

### Visualizations

- Histograms
- Count Plots
- Correlation Heatmap
- Category-wise Recurrence Analysis

---

## Correlation Analysis

A comprehensive correlation matrix was generated to identify relationships among features and their association with cancer recurrence.

Insights from the heatmap helped in understanding which clinical variables were most relevant for prediction.

---

## Outlier Analysis

Outlier detection was performed on the Age feature using the Interquartile Range (IQR) method.

### Steps

- Calculate Q1 and Q3
- Compute IQR
- Determine lower and upper bounds
- Identify potential age outliers

This analysis helped assess data quality before model training.

---

## Machine Learning Model

### Logistic Regression

A Logistic Regression classifier was used to predict thyroid cancer recurrence.

Reasons for selecting Logistic Regression:

- Strong baseline classification algorithm
- Highly interpretable results
- Efficient on structured medical datasets
- Suitable for binary classification problems

---

## Model Training

### Train-Test Split

- Training Data: 70%
- Testing Data: 30%

### Algorithm

- Logistic Regression

---

## Evaluation Metrics

The model was evaluated using:

- Accuracy Score
- Precision Score
- Recall Score
- Confusion Matrix
- Classification Report

Additional evaluation included:

- Class-wise Precision
- Class-wise Recall
- F1-Score

---

## Results

The Logistic Regression model demonstrated strong predictive capability for identifying patients at risk of thyroid cancer recurrence.

Key observations:

- High overall classification performance
- Effective discrimination between recurrence and non-recurrence cases
- Strong balance between precision and recall
- Useful predictive capability for clinical risk assessment

These results indicate that machine learning can support oncologists in identifying patients who may require closer follow-up after treatment.

---

## Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-Learn

---

## Key Learnings

- Importance of categorical feature encoding
- Benefits of correlation analysis in healthcare datasets
- Clinical relevance of cancer staging information
- Application of Logistic Regression in medical prediction tasks
- Importance of feature engineering for structured healthcare data

---

## Future Improvements

- Hyperparameter Optimization
- Ensemble Learning Methods
- XGBoost and LightGBM Comparison
- SHAP Explainability Analysis
- Risk Stratification Dashboard
- Clinical Decision Support System Integration

---

## Author

**Chaitali Jadhav**

Data Analytics | Machine Learning | Healthcare AI | Deep Learning
