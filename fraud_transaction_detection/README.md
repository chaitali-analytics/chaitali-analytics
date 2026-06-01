# Fraud Transaction Detection using Machine Learning

## Overview

This project focuses on detecting fraudulent financial transactions using machine learning and advanced feature engineering techniques.

The workflow includes:

* Combining multiple transaction datasets stored as `.pkl` files
* Exploratory Data Analysis (EDA)
* Fraud pattern visualization
* Time-based feature engineering
* Rolling-window behavioral features
* Random Forest classification
* Data leakage investigation and mitigation
* Performance evaluation using classification metrics and ROC-AUC

The project demonstrates how improper feature selection can lead to misleadingly perfect fraud detection performance and highlights the importance of identifying and removing data leakage.

---

## Dataset

The dataset consists of multiple daily transaction files stored in `.pkl` format.

Each transaction contains information such as:

* Transaction ID
* Customer ID
* Terminal ID
* Transaction Amount
* Transaction Timestamp
* Fraud Label
* Fraud Scenario

### Target Variable

| Column   | Description                                            |
| -------- | ------------------------------------------------------ |
| TX_FRAUD | 0 = Legitimate Transaction, 1 = Fraudulent Transaction |

---

## Project Workflow

### 1. Data Loading

* Mounted Google Drive
* Loaded all `.pkl` files
* Combined them into a single DataFrame

```python
combined_df = pd.concat(all_dfs, ignore_index=True)
```

---

### 2. Exploratory Data Analysis (EDA)

Several visualizations were created to understand fraud behavior:

### Fraud Distribution

* Fraud vs Non-Fraud transactions
* Fraud scenarios

### Transaction Amount Distribution

* Histogram of transaction amounts
* Detection of high-value transactions

### Time-Based Analysis

* Transaction Amount vs Transaction Time
* Fraud transactions by scenario over time

### Fraud Amount Analysis

* Boxplots comparing fraud and non-fraud transactions
* High-value fraud detection patterns

---

## Feature Engineering

### Time-Based Features

Extracted temporal information from transaction timestamps:

```python
TX_HOUR_OF_DAY
TX_DAY_OF_WEEK
TX_DAY_OF_MONTH
TX_MONTH
TX_YEAR
```

These features help capture fraud patterns occurring during specific periods.

---

### Rolling Window Features

Behavioral features were created using a 1-day rolling window.

#### Customer Features

```python
CUSTOMER_AVG_TX_1DAY
CUSTOMER_TX_COUNT_1DAY
```

#### Terminal Features

```python
TERMINAL_AVG_TX_1DAY
TERMINAL_TX_COUNT_1DAY
```

These features provide context about:

* Customer spending behavior
* Transaction frequency
* Terminal activity patterns

---

## Train-Test Split

A chronological split was used to avoid future information leakage.

| Dataset    | Percentage |
| ---------- | ---------- |
| Training   | 70%        |
| Validation | 15%        |
| Testing    | 15%        |

```python
train_df = combined_df.iloc[:train_split_idx]
val_df = combined_df.iloc[train_split_idx:val_split_idx]
test_df = combined_df.iloc[val_split_idx:]
```

---

## Model Used

### Random Forest Classifier

```python
RandomForestClassifier(
    random_state=42,
    n_jobs=-1
)
```

Why Random Forest?

* Handles nonlinear relationships
* Robust to noisy features
* Works well on tabular transaction data
* Provides feature importance analysis

---

## Evaluation Metrics

The model was evaluated using:

* Precision
* Recall
* F1 Score
* ROC-AUC Score
* ROC Curve

```python
classification_report()
roc_auc_score()
roc_curve()
```

---

# Initial Results

The first model achieved:

| Metric    | Score  |
| --------- | ------ |
| Precision | 1.00   |
| Recall    | 1.00   |
| F1 Score  | 1.00   |
| ROC-AUC   | 1.0000 |

While impressive, such perfect performance is highly unusual in real-world fraud detection systems.

This prompted an investigation into possible **data leakage**.

---

# Data Leakage Investigation

Two suspicious features were identified:

### 1. TX_FRAUD_SCENARIO

This column directly describes the fraud type.

Examples:

* Scenario 1
* Scenario 2
* Scenario 3

Since this information would not be available at prediction time, it leaks target information.

---

### 2. is_outlier

```python
is_outlier = TX_AMOUNT > 300
```

This feature was highly correlated with fraudulent transactions.

Analysis revealed that high-value transactions were disproportionately fraudulent.

---

## Removing Leaky Features

The following features were removed:

```python
TX_FRAUD_SCENARIO
is_outlier
```

The model was then retrained using only legitimate predictive features.

---

# Retrained Model Results

| Metric    | Score  |
| --------- | ------ |
| Precision | 1.00   |
| Recall    | 0.21   |
| F1 Score  | 0.34   |
| ROC-AUC   | 0.6224 |

---

## Findings

### Before Leakage Removal

```text
Precision: 1.00
Recall: 1.00
F1 Score: 1.00
ROC-AUC: 1.0000
```

### After Leakage Removal

```text
Precision: 1.00
Recall: 0.21
F1 Score: 0.34
ROC-AUC: 0.6224
```

The dramatic performance drop confirms that the original model was relying heavily on leaked information rather than learning genuine fraud patterns.

---

## Key Learnings

### Importance of Feature Engineering

Rolling customer and terminal behavior significantly improved contextual understanding.

### Importance of Temporal Splits

Chronological train-test splitting prevents future information leakage.

### Detecting Data Leakage

Perfect model performance should always be treated with skepticism.

Features that directly reveal target information can create unrealistic results.

### Realistic Fraud Detection

After removing leakage, the model provides a much more honest assessment of fraud detection capability.

---

## Technologies Used

* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Scikit-learn
* Google Colab

---

## Future Improvements

* XGBoost
* LightGBM
* CatBoost
* SMOTE for class imbalance
* Isolation Forest for anomaly detection
* Graph-based fraud detection
* Deep learning approaches (LSTM, Autoencoders)
* Real-time fraud scoring pipeline

---

## Conclusion

This project demonstrates a complete fraud detection workflow from raw transaction logs to machine learning deployment readiness. A major contribution of the work is the identification and removal of data leakage, transforming an unrealistically perfect model into a realistic fraud detection system that better reflects real-world performance.
