# 📱 Mobile Phone Price Range Prediction

## Overview

This project focuses on predicting the price range of mobile phones based on their technical specifications using machine learning classification algorithms.

The objective is to classify mobile devices into predefined price categories by analyzing hardware and performance-related features such as battery capacity, RAM, internal memory, processor specifications, display characteristics, and connectivity options.

The project includes comprehensive exploratory data analysis, feature relationship analysis, anomaly detection, feature scaling, model training, and performance comparison across multiple machine learning algorithms.

---

## Problem Statement

Mobile phone manufacturers and e-commerce platforms often need to estimate the pricing category of a device based on its specifications.

This project aims to build predictive models capable of automatically classifying mobile phones into appropriate price ranges.

---

## Dataset Features

The dataset contains technical specifications including:

- Battery Power
- RAM
- Internal Memory
- Mobile Depth
- Mobile Weight
- Number of Processor Cores
- Pixel Resolution Height
- Pixel Resolution Width
- Screen Height
- Screen Width
- Talk Time
- Clock Speed
- Front Camera Resolution
- Primary Camera Resolution
- Connectivity Features
- Touch Screen Availability
- WiFi Support

### Target Variable

`price_range`

| Class | Description |
|---------|-------------|
| 0 | Low Cost |
| 1 | Medium Cost |
| 2 | High Cost |
| 3 | Premium Cost |

---

## Exploratory Data Analysis

Several visualization techniques were used to understand data patterns and relationships.

### Feature Distribution Analysis

Histograms were generated for all features grouped by price category to identify trends and separability among classes.

### Correlation Analysis

A correlation heatmap was created to identify relationships between features and detect potential multicollinearity.

Key observations:

- RAM showed strong positive correlation with price range.
- Battery power contributed significantly to pricing.
- Pixel resolution features were positively associated with higher-priced devices.

---

## Outlier Detection

Isolation Forest was used to identify anomalous observations.

### Method

- Isolation Forest
- Contamination Rate: 1%
- Random State: 42

Additional features generated:

- Outlier Prediction
- Anomaly Score

This analysis helped evaluate data quality and understand unusual device configurations.

---

## Data Preprocessing

### Feature Selection

Target variable and anomaly-related columns were removed from the training feature set.

### Train-Test Split

- Training Data: 80%
- Testing Data: 20%

### Feature Scaling

StandardScaler was applied to normalize feature values.

Feature scaling was particularly important for:

- Support Vector Machine
- Distance-based learning behavior

---

## Machine Learning Models

### 1. Random Forest Classifier

Random Forest was trained using ensemble learning through multiple decision trees.

#### Performance

Accuracy: **89.25%**

Strengths:

- Robust against noise
- Handles nonlinear relationships effectively
- Strong overall classification performance

---

### 2. Support Vector Machine (SVM)

A Support Vector Classifier was trained using scaled features.

#### Performance

Accuracy: **89.25%**

Strengths:

- Effective in high-dimensional spaces
- Strong decision boundaries
- Competitive performance across all classes

---

### 3. XGBoost Classifier

Extreme Gradient Boosting was used as an advanced ensemble learning approach.

#### Performance

Accuracy: **90.50%**

Strengths:

- Superior predictive power
- Efficient handling of complex feature interactions
- Better class-wise recall and precision

---

## Model Comparison

| Model | Accuracy |
|---------|-----------|
| Random Forest | 89.25% |
| SVM | 89.25% |
| XGBoost | **90.50%** |

---

## Results

Among all evaluated models, XGBoost achieved the highest overall accuracy and demonstrated the most balanced performance across all price categories.

The confusion matrix and classification reports indicated fewer misclassifications and stronger recall for intermediate and premium price classes.

---

## Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-Learn
- XGBoost

---

## Key Learnings

- Feature scaling significantly improves SVM performance.
- RAM and display specifications are strong predictors of price range.
- Ensemble learning methods outperform individual classifiers.
- XGBoost provides the best balance between accuracy and generalization.

---

## Future Improvements

- Hyperparameter optimization using GridSearchCV
- Feature importance analysis using SHAP
- Model deployment using Flask or Streamlit
- Real-world pricing estimation using regression techniques

---

## Author

**Chaitali Jadhav**

Data Analytics | Machine Learning | Healthcare AI | Deep Learning
