#  Lung Cancer Survival Prediction using Machine Learning

##  Project Overview

This project focuses on predicting the survival outcome of lung cancer patients using machine learning techniques. The dataset contains patient demographics, medical history, treatment information, and clinical measurements.

The objective is to build predictive models that can estimate whether a patient survives based on their medical and treatment-related attributes. Multiple classification algorithms were evaluated and compared to identify the most suitable model for handling an imbalanced healthcare dataset.

---

##  Objectives

- Perform data cleaning and preprocessing.
- Engineer meaningful features from clinical records.
- Handle missing values and categorical variables.
- Scale numerical features for model training.
- Train multiple machine learning classification models.
- Compare model performance using classification metrics.
- Identify the most effective model for patient survival prediction.

---

##  Dataset Features

The dataset contains information such as:

| Feature | Description |
|-----------|------------|
| age | Patient age |
| gender | Male/Female |
| country | Patient country |
| bmi | Body Mass Index |
| cholesterol_level | Cholesterol measurement |
| family_history | Family history of cancer |
| smoking_status | Smoking behavior |
| cancer_stage | Stage of cancer |
| treatment_type | Type of treatment received |
| diagnosis_date | Date of diagnosis |
| end_treatment_date | Treatment completion date |
| survived | Target variable |

---

#  Data Preprocessing

## 1. Data Cleaning

- Removed records with missing target values (`survived`).
- Checked dataset structure and descriptive statistics.
- Identified missing values across features.

### Missing Value Handling

Rows with missing survival outcomes were removed to ensure reliable model training.

---

## 2. Feature Engineering

### Treatment Duration

Created a new feature:

```python
treatment_duration =
end_treatment_date - diagnosis_date
```

This captures the duration of treatment in days.

### Family History Encoding

Converted:

| Original | Encoded |
|-----------|---------|
| Yes | 1 |
| No | 0 |

### Removed Columns

The following columns were dropped:

- `id`
- `diagnosis_date`
- `end_treatment_date`

because they were either identifiers or already represented through engineered features.

---

## 3. Categorical Encoding

Applied One-Hot Encoding using:

```python
pd.get_dummies()
```

Encoded categorical variables:

- gender
- country
- cancer_stage
- smoking_status
- treatment_type

This transformed all categorical information into machine-learning-friendly numerical features.

---

## 4. Feature Scaling

Standardized numerical variables using `StandardScaler`.

Scaled features:

- age
- bmi
- cholesterol_level
- treatment_duration

Formula:

\[
Z = \frac{X - \mu}{\sigma}
\]

This ensures equal contribution of numerical features during model training.

---

#  Machine Learning Models

The following classification algorithms were trained and evaluated:

## 1. Logistic Regression

```python
LogisticRegression(
    class_weight='balanced'
)
```

---

## 2. Random Forest Classifier

```python
RandomForestClassifier(
    class_weight='balanced'
)
```

---

## 3. Decision Tree Classifier

```python
DecisionTreeClassifier(
    class_weight='balanced'
)
```

---

## 4. XGBoost Classifier

```python
XGBClassifier(
    scale_pos_weight=...
)
```

---

## 5. Linear Support Vector Machine (SVM)

```python
LinearSVC(
    class_weight='balanced'
)
```

---

#  Model Evaluation Metrics

Models were evaluated using:

- Accuracy
- Precision
- Recall
- F1 Score

These metrics are especially important because the dataset exhibits class imbalance.

---

#  Performance Comparison

| Model | Accuracy | Precision | Recall | F1 Score |
|---------|---------|---------|---------|---------|
| Logistic Regression | 0.4860 | 0.2201 | **0.5245** | **0.3101** |
| Random Forest | **0.7794** | 0.5000 | 0.0005 | 0.0010 |
| Decision Tree | 0.6477 | 0.2181 | 0.2319 | 0.2248 |
| XGBoost | 0.5134 | 0.2221 | 0.4832 | 0.3043 |
| Linear SVM | 0.4905 | 0.2200 | 0.5159 | 0.3084 |

---

#  Best Model

## Logistic Regression

### Why?

Although Random Forest achieved the highest overall accuracy, it almost completely failed to identify positive survival cases.

Logistic Regression achieved:

- Highest Recall
- Highest F1 Score
- Better minority class detection
- More balanced performance

### Final Metrics

| Metric | Score |
|----------|--------|
| Accuracy | 48.60% |
| Precision | 22.01% |
| Recall | **52.45%** |
| F1 Score | **31.01%** |

---

#  Key Insights

### Class Imbalance Matters

The dataset contains significantly fewer survival cases than non-survival cases.

High accuracy alone is misleading because a model can predict the majority class and still achieve good accuracy.

---

### Recall is Critical

In healthcare applications:

- Missing a patient likely to survive can be costly.
- Recall becomes more important than raw accuracy.

Therefore, Logistic Regression is preferred despite its lower accuracy.

---

### Importance of Feature Engineering

Creating:

- Treatment Duration
- Encoded Family History

helped capture clinically meaningful patterns that improved predictive performance.

---

### Balancing Techniques Helped

The use of:

```python
class_weight='balanced'
```

and

```python
scale_pos_weight
```

helped models pay more attention to the minority class.

---

#  Technologies Used

- Python
- Pandas
- NumPy
- Scikit-Learn
- XGBoost
- Matplotlib
- Seaborn

---

#  Future Improvements

- Hyperparameter tuning using GridSearchCV
- SMOTE oversampling for imbalance handling
- Ensemble learning approaches
- Feature selection techniques
- Deep Learning models
- Survival Analysis models (Cox Regression)
- Explainable AI (SHAP/LIME)

---

#  Conclusion

This project demonstrates a complete machine learning workflow for predicting lung cancer patient survival.

After preprocessing, feature engineering, scaling, and model comparison, **Logistic Regression emerged as the most suitable model** due to its superior ability to identify survival cases in an imbalanced dataset.

The project highlights the importance of choosing evaluation metrics carefully in healthcare applications, where detecting minority-class outcomes is often more important than maximizing overall accuracy.
