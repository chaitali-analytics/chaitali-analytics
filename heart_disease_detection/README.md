# ❤️ Heart Disease Detection using Machine Learning

## Project Overview

Heart disease is one of the leading causes of death worldwide. Early prediction of cardiovascular disease can help healthcare professionals provide timely treatment and improve patient outcomes.

This project develops a machine learning-based Heart Disease Detection system using clinical and patient health attributes. The workflow includes data preprocessing, feature scaling, exploratory data analysis (EDA), outlier handling, feature transformation, and classification using a LightGBM model.

The objective is to accurately predict the presence of heart disease and evaluate model performance using multiple classification metrics.

---

## Dataset Information

The dataset contains patient health information and clinical measurements commonly associated with cardiovascular disease risk.

### Features Used

- Age
- Sex
- Chest Pain Type
- Resting Blood Pressure
- Cholesterol
- Fasting Blood Sugar
- Resting ECG
- Maximum Heart Rate
- Exercise-Induced Angina
- Oldpeak
- ST Slope
- Additional clinical indicators

### Target Variable

- **Target**
  - 0 → No Heart Disease
  - 1 → Heart Disease Present

---

## Project Workflow

### 1. Data Exploration

Initial dataset inspection included:

- Dataset structure analysis
- Data type verification
- Descriptive statistical analysis
- Feature distribution analysis

---

### 2. Data Preprocessing

Numerical features were standardized using **StandardScaler** to normalize feature ranges and improve model performance.

Scaled Features:

- Resting Blood Pressure
- Cholesterol
- Maximum Heart Rate
- Oldpeak

---

### 3. Exploratory Data Analysis (EDA)

Several visualizations were created to understand feature behavior and disease patterns:

- Feature distribution histograms
- Disease-wise feature comparisons
- Correlation heatmap
- Boxplots for outlier analysis

---

### 4. Outlier Detection and Handling

Outliers were identified using the **Interquartile Range (IQR)** method.

#### Winsorization (Capping)

Extreme values were capped using upper and lower IQR boundaries to reduce the impact of anomalies.

#### Power Transformation

The following features were transformed using the **Yeo-Johnson Power Transformation**:

- Resting Blood Pressure
- Cholesterol
- Oldpeak

Benefits:

- Reduced skewness
- Improved feature distributions
- Enhanced model stability

---

## Machine Learning Model

### LightGBM Classifier

A **Light Gradient Boosting Machine (LightGBM)** model was trained to classify heart disease occurrence.

LightGBM was selected because of:

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

- LightGBM Classifier

---

## Evaluation Metrics

The model was evaluated using multiple classification metrics:

- Accuracy Score
- Precision Score
- Confusion Matrix
- Classification Report

Additional performance indicators:

- Class-wise Precision
- Class-wise Recall
- F1-Score

---

## Results

The LightGBM model demonstrated strong predictive capability for identifying heart disease patients.

Performance evaluation showed:

- High classification accuracy
- Strong precision and recall balance
- Effective identification of disease-positive patients
- Low false-negative rate

These results indicate that the model can serve as a useful decision-support tool for cardiovascular risk assessment.

---

## Technologies Used

### Programming

- Python

### Data Analysis

- Pandas
- NumPy

### Data Visualization

- Matplotlib
- Seaborn

### Machine Learning

- Scikit-Learn
- LightGBM

---

## Key Learnings

- Medical datasets often require careful handling of outliers.
- Feature transformation can significantly improve model stability.
- LightGBM performs exceptionally well on structured healthcare datasets.
- Exploratory Data Analysis is critical for identifying clinically relevant predictors.
- Proper preprocessing directly influences predictive performance.

---

## Future Improvements

- Hyperparameter tuning using GridSearchCV
- SHAP Explainability Analysis
- Feature Importance Ranking
- Ensemble Learning Approaches
- Deployment as a Clinical Decision Support Application

---

## Author

**Chaitali Jadhav**

Data Analytics | Machine Learning | Healthcare AI | Deep Learning
