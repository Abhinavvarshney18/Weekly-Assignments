# Week 1 Assignment - E-commerce EDA Scenario Challenge

## Student Details

**Name:** Abhinav Varshney
**University:** GLA University, Mathura
**Course:** B.Tech AIML

---

## Project Overview

This project focuses on Exploratory Data Analysis (EDA), data preprocessing, feature engineering, and business insight generation using a large-scale e-commerce dataset containing 500,000 records.

The objective is to analyze customer purchasing behavior, identify factors influencing product returns, and prepare data for future machine learning models.

---

## Dataset Information

* Total Records: 500,000
* Total Features: 30
* Dataset Type: E-commerce Transactions
* Target Variable: `is_returned`

---

## Assignment Tasks Completed

### Phase 1: Data Audit

* Checked dataset dimensions
* Identified missing values
* Analyzed data types
* Detected categorical and numerical features

### Phase 2: Price Distribution Analysis

* Examined pricing features
* Checked skewness
* Identified outliers
* Suggested log transformation

### Phase 3: Categorical Feature Analysis

* Identified categorical columns
* Detected high-cardinality features
* Recommended encoding techniques

### Phase 4: Return Pattern Analysis

* Calculated return rates
* Analyzed return reasons
* Generated business insights

### Phase 5: Feature Engineering

* Missing value handling
* Feature scaling
* One-Hot Encoding
* Ordinal Encoding
* ColumnTransformer Pipeline

### Phase 6: Correlation Analysis

* Correlation matrix study
* Feature importance analysis
* Return prediction insights

---

## Technologies Used

* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Scikit-Learn

---

## Repository Structure

```
Week1_Assignment/
│
├── ecommerce_500k.csv
├── customer-churn-prediction.ipynb
├── answers.md
└── README.md
```

---

## Key Findings

* Pricing data is positively skewed.
* Missing values exist in multiple columns.
* City feature contains high cardinality.
* Product returns are mainly caused by:

  * Not as Described
  * Defective Products
  * Wrong Item Delivered
  * Better Price Found

---

## Conclusion

The dataset was successfully audited and analyzed. Important business insights were identified, and a complete preprocessing pipeline was designed to support future machine learning models for return prediction.

---

**Submitted for Week 1 Assignment**
