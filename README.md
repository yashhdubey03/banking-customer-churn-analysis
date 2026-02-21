# Banking Customer Churn Analysis

Customer retention is one of the most critical drivers of long-term profitability in the banking sector. Even small increases in churn can significantly impact revenue, customer lifetime value, and competitive positioning.

This project explores customer churn behavior within a banking scenario using demographic, transactional, service interaction, and digital engagement data. The objective of Phase 1 was to integrate multiple data sources, conduct exploratory analysis, and engineer meaningful features to prepare the dataset for predictive modeling.

Phase 2 extends this work by developing and evaluating machine learning models to identify customers at risk of churn and assess whether meaningful predictive signal exists in the data.

---

## Table of Contents

- [The Problem](#the-problem)
- [Approach](#approach)
- [Key Insights from Exploratory Analysis](#key-insights-from-exploratory-analysis)
- [Machine Learning Modeling](#machine-learning-modeling)
- [Model Results](#model-results)
- [Tools & Technologies](#tools--technologies)
- [Project Status](#project-status)

---

## The Problem

The dataset consists of 1,000 customers, with a churn rate of **20.4%**. The goal is to identify early indicators of customer attrition and understand whether churn is driven by demographics, service dissatisfaction, financial activity, or behavioral disengagement.

---

## Approach

To simulate a real-world analytics workflow, the project was structured as a multi-stage data pipeline:

1. **Data Integration**
   - Merged customer demographics, transaction history, service interactions, online activity, and churn status using a common customer identifier.
   - Aggregated transaction-level and service-level records into customer-level features.

2. **Feature Engineering**
   - Created engagement metrics such as total transactions and average spending.
   - Engineered service-related indicators including complaint count and unresolved cases.
   - Transformed login dates into a behavioral inactivity metric: **Days Since Last Login**.

3. **Data Validation**
   - Handled missing values.
   - Ensured consistency across merged datasets.
   - Prepared a clean modeling-ready dataset.

---

## Key Insights from Exploratory Analysis

The analysis revealed that churn behavior in this dataset is subtle and not driven by a single dominant factor.

- **Digital engagement is the strongest signal.** Customers with lower login frequency and higher inactivity show a slightly higher likelihood of churn.
- **Demographic factors have limited influence.** Gender, marital status, and income levels show minimal separation between churned and retained groups.
- **Service complaints alone do not strongly predict churn.** Dissatisfaction may interact with other behavioral factors rather than acting independently.
- **Financial activity is not sufficient on its own.** Spending and transaction counts show only minor differences.

Overall, churn appears to be influenced by multiple interacting behavioral patterns rather than isolated variables.

---

## Machine Learning Modeling

Following exploratory analysis and feature preparation, Phase 2 focused on building predictive models to estimate churn probability.

The modeling workflow was designed to follow industry best practices:

- Preprocessing pipelines to prevent data leakage  
- Stratified cross-validation for robust evaluation  
- Handling class imbalance using class weighting and SMOTE  
- Comparison of multiple algorithms to assess predictive signal  

The models evaluated included:

- Dummy classifier (baseline)
- Logistic Regression
- Random Forest
- Random Forest with SMOTE
- Gradient Boosting
- Tuned Gradient Boosting (GridSearchCV)

ROC-AUC was used as the primary evaluation metric because it provides a threshold-independent measure of performance suitable for imbalanced classification problems.

---

## Model Results

The analysis showed that predictive signal in the dataset is present but modest.

Non-linear ensemble methods performed better than linear models, indicating that churn behavior is influenced by complex interactions rather than simple relationships.

### Model Performance Comparison

| Model | Mean ROC-AUC |
|-------|-------------|
Dummy | 0.50 |
Logistic Regression | 0.52 |
Random Forest | 0.54 |
Random Forest + SMOTE | 0.53 |
Gradient Boosting | 0.55 |
Gradient Boosting (Tuned) | **0.57** |

The tuned Gradient Boosting model achieved the best performance.

Feature importance analysis indicated that **customer engagement and spending behavior** were the strongest predictors of churn risk, particularly:

- Average spending
- Total spending
- Login frequency
- Days since last login

These findings are consistent with the exploratory analysis, reinforcing the importance of behavioral engagement signals.

---

## Tools & Technologies

- Python
- Pandas & NumPy
- Seaborn & Matplotlib
- Scikit-learn
- Imbalanced-learn (SMOTE)
- Google Colab

---

## Project Status

**Phase 1 Complete**  
Data integration, exploratory analysis, and feature engineering finalized.

**Phase 2 Complete**  
Machine learning modeling, evaluation, and feature importance analysis completed.

This project demonstrates an end-to-end banking analytics workflow from raw data integration to predictive modeling and business insight generation.

---
