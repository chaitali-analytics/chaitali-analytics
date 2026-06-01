# Liver Cirrhosis Stage Detection using Machine Learning

## Project Overview

This project focuses on predicting the stage of Liver Cirrhosis using clinical, laboratory, and patient demographic information. Liver cirrhosis is a chronic liver disease that progresses through multiple stages, making early and accurate stage identification critical for treatment planning and patient management.

The project includes data preprocessing, categorical feature encoding, exploratory data analysis, correlation analysis, anomaly detection, feature scaling, and comparative evaluation of multiple machine learning algorithms.

---

## Problem Statement

Liver cirrhosis is a progressive disease that can lead to severe complications if not detected and managed appropriately.

The objective of this project is to develop machine learning models capable of accurately classifying patients into different cirrhosis stages using medical and laboratory measurements.

---

## Dataset Features

The dataset contains clinical and laboratory information including:

### Demographic Features

* Age
* Sex

### Treatment Information

* Drug Type

### Clinical Features

* Ascites
* Hepatomegaly
* Spiders
* Edema

### Laboratory Measurements

* Bilirubin
* Cholesterol
* Albumin
* Copper
* Alkaline Phosphatase
* SGOT
* Triglycerides
* Platelets
* Prothrombin

### Patient Status Information

* Status

### Target Variable

* Stage

Classes:

* Stage 1
* Stage 2
* Stage 3
* Stage 4

---

## Data Preprocessing

### Categorical Feature Encoding

Several categorical features were converted into numerical representations.

#### Status Encoding

* C → 0
* CL → 1
* D → 2

#### Drug Encoding

* Placebo → 0
* D-penicillamine → 1

#### Sex Encoding

* Female → 0
* Male → 1

#### Edema Encoding

* N → 0
* S → 1
* Y → 2

#### Binary Feature Encoding

Applied to:

* Ascites
* Spiders
* Hepatomegaly

Encoding:

* No → 0
* Yes → 1

---

## Exploratory Data Analysis

Extensive EDA was performed to understand feature distributions and stage-wise differences.

### Analyses Performed

* Feature Distribution Analysis
* Stage-wise Comparison
* Correlation Analysis
* Outlier Detection

### Visualizations

* Histograms
* Multi-Class Distribution Plots
* Correlation Heatmap
* Anomaly Score Distribution

---

## Correlation Analysis

A complete correlation matrix was generated to understand relationships among clinical variables and liver cirrhosis stages.

The heatmap helped identify:

* Strongly correlated laboratory features
* Variables associated with disease progression
* Potential predictive biomarkers

---

## Outlier Detection

### Isolation Forest

Anomaly detection was performed using the Isolation Forest algorithm.

#### Steps

* Train Isolation Forest model
* Calculate anomaly scores
* Identify abnormal observations
* Visualize anomaly score distribution

Additional features generated:

* outlier_pred
* anomaly_score

This process helped evaluate the presence of unusual patient records without removing potentially important clinical cases.

---

## Feature Scaling

To ensure consistent model performance, numerical features were standardized using StandardScaler.

Benefits:

* Improved optimization
* Faster convergence
* Better performance for distance-based algorithms
* Enhanced SVM and Neural Network training

---

## Train-Test Split

* Training Data: 80%
* Testing Data: 20%

---

# Machine Learning Models

Multiple classification algorithms were trained and compared.

---

## 1. Logistic Regression

A multiclass Logistic Regression model was trained as a baseline classifier.

### Advantages

* Simple and interpretable
* Fast training
* Strong baseline performance

### Evaluation Metrics

* Accuracy Score
* R² Score
* Confusion Matrix
* Classification Report

---

## 2. Decision Tree Classifier

A Decision Tree model was used to capture nonlinear decision boundaries.

### Advantages

* Easy interpretation
* Handles feature interactions
* Captures nonlinear relationships

### Evaluation Metrics

* Accuracy Score
* Confusion Matrix
* Classification Report

---

## 3. Support Vector Machine (SVM)

An SVM classifier was trained using scaled features.

### Advantages

* Effective in high-dimensional spaces
* Strong classification performance
* Robust decision boundaries

### Evaluation Metrics

* Accuracy Score
* Confusion Matrix
* Classification Report

---

## 4. XGBoost Classifier

An Extreme Gradient Boosting model was trained for multiclass classification.

### Advantages

* High predictive accuracy
* Handles nonlinear relationships
* Built-in regularization
* Robust against overfitting

### Evaluation Metrics

* Accuracy Score
* Confusion Matrix
* Classification Report

---

## 5. K-Nearest Neighbors (KNN)

A KNN classifier was implemented using:

* K = 5

### Advantages

* Simple algorithm
* Effective for local pattern recognition
* No assumptions about data distribution

### Evaluation Metrics

* Accuracy Score
* Confusion Matrix
* Classification Report

---

## 6. Naive Bayes Classifier

A Gaussian Naive Bayes model was trained.

### Advantages

* Fast training
* Works well with smaller datasets
* Probabilistic predictions

### Evaluation Metrics

* Accuracy Score
* Confusion Matrix
* Classification Report

---

## 7. Neural Network (MLP Classifier)

A Multi-Layer Perceptron (MLP) Neural Network was trained.

### Configuration

* Maximum Iterations: 1000
* Random State: 42

### Advantages

* Learns complex nonlinear relationships
* Captures hidden patterns in clinical data
* Strong predictive capability

### Evaluation Metrics

* Accuracy Score
* Confusion Matrix
* Classification Report

---

## Model Comparison

The project compared seven machine learning algorithms:

| Model               | Purpose                       |
| ------------------- | ----------------------------- |
| Logistic Regression | Baseline Model                |
| Decision Tree       | Rule-Based Classification     |
| SVM                 | Margin-Based Classification   |
| XGBoost             | Gradient Boosting             |
| KNN                 | Distance-Based Classification |
| Naive Bayes         | Probabilistic Classification  |
| Neural Network      | Deep Pattern Learning         |

This comparative analysis helped identify the most effective model for liver cirrhosis stage prediction.

---

## Results

The models demonstrated varying levels of performance across the four cirrhosis stages.

Key observations:

* Ensemble methods showed strong predictive capability.
* Neural Networks captured complex nonlinear relationships.
* SVM performed effectively after feature scaling.
* Tree-based methods handled mixed clinical features efficiently.
* Model comparison provided valuable insight into the most suitable approach for medical stage classification.

The study demonstrates that machine learning can effectively support liver disease staging and clinical decision-making.

---

## Technologies Used

* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Scikit-Learn
* XGBoost

---

## Key Learnings

* Importance of feature scaling in healthcare datasets
* Application of anomaly detection using Isolation Forest
* Benefits of comparing multiple machine learning algorithms
* Handling multiclass medical classification problems
* Understanding strengths and limitations of different classifiers

---

## Future Improvements

* Hyperparameter Optimization
* Feature Selection Techniques
* Cross-Validation Analysis
* LightGBM and CatBoost Comparison
* SHAP Explainability Analysis
* Ensemble Stacking Models
* Clinical Decision Support Dashboard

---

## Author

**Chaitali Jadhav**

Data Analytics | Machine Learning | Healthcare AI | Deep Learning

