# DA5401 Assignment 6: Imputation via Regression for Missing Data

- **Name**: Rishabh Gupta
- **Roll Number**: DA25M024

---

## Project Overview

This assignment explores **regression-based imputation techniques** for handling missing data in the **UCI Credit Card Default dataset**.  
The primary goal is to compare different imputation strategies and evaluate their impact on **credit risk classification performance** using logistic regression models.

---

## Dataset

- **Dataset Name**: UCI Credit Card Default Clients Dataset
- **Source**: Kaggle - Default of Credit Card Clients
- **Description**: Contains credit card client information including payment history, bill statements, and demographic data.
- **Preprocessing Steps**:
  - Column name cleaning and standardization  
  - Introduction of Missing At Random (MAR) values (5% in AGE and BILL_AMT1 columns)
  - Feature scaling using StandardScaler
  - Train-test split with stratification

---

## Essential Files for Evaluation

1. **DA_LAB_A6.ipynb**  
   – Main Jupyter Notebook containing:
     - Data preprocessing and MAR introduction  
     - Three imputation strategies implementation
     - Logistic regression model training and evaluation
     - Comprehensive performance comparison
     - Insights and recommendations

2. **README.md**  
   – This documentation file.

3. **UCI_Credit_Card.csv**  
   – Original dataset used for all analyses.

---

## Implementation Details

### Key Libraries Used
- **pandas**, **numpy** → Data manipulation and missing value handling
- **matplotlib**, **seaborn** → Performance visualization and comparison
- **scikit-learn** → Regression models, imputation, and classification
- **SimpleImputer** → Baseline median imputation

---

### Approach

1. **Data Preparation**
   - Load and clean the dataset
   - Introduce 5% MAR values in AGE and BILL_AMT1 columns
   - Verify random missingness through correlation analysis

2. **Imputation Strategies (Part A)**
   - **Median Imputation**: Simple baseline approach
   - **Linear Regression Imputation**: Predict missing values using linear relationships
   - **KNN Regression Imputation**: Non-linear approach using nearest neighbors
   - **Listwise Deletion**: Traditional approach for comparison

3. **Model Evaluation (Part B)**
   - Train Logistic Regression classifiers on each imputed dataset
   - Evaluate using Accuracy, Precision, Recall, and F1-Score
   - Compare performance across all strategies

4. **Comparative Analysis (Part C)**
   - Analyze trade-offs between imputation and deletion
   - Compare linear vs non-linear regression performance
   - Provide business recommendations based on results

---

## Key Findings

### Performance Metrics Summary:
| Method | Accuracy | Precision | Recall | F1-Score |
|--------|----------|-----------|--------|----------|
| Median Imputation | 0.8075 | 0.6845 | 0.2404 | 0.3558 |
| Linear Regression | 0.8080 | 0.6882 | 0.2411 | 0.3571 |
| KNN Regression | 0.8077 | 0.6852 | 0.2411 | 0.3567 |
| Listwise Deletion | 0.8045 | 0.6735 | 0.2209 | 0.3327 |

### Main Insights:
- **All imputation methods outperformed listwise deletion**
- **Linear regression imputation achieved the best F1-score**
- **Data preservation (30,000 samples) proved crucial for performance**
- **Linear relationships dominated for BILL_AMT1 feature imputation**

