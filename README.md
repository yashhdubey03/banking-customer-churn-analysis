# Banking Customer Churn Analysis

Customer retention is one of the most critical drivers of long-term profitability in the banking sector. Even small increases in churn can significantly impact revenue, customer lifetime value, and competitive positioning.

This project explores customer churn behavior within a banking scenario using demographic, transactional, service interaction, and digital engagement data. The objective of Phase 1 was to integrate multiple data sources, conduct exploratory analysis, and engineer meaningful features to prepare the dataset for predictive modeling.

---

## Table of Contents

- [The Problem](#the-problem)
- [Approach](#approach)
- [Key Insights from Exploratory Analysis](#key-insights-from-exploratory-analysis)
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

## Tools & Technologies

- Python
- Pandas & NumPy
- Seaborn & Matplotlib
- Google Colab

---

## Project Status

**Phase 1 Complete**  
Data integration, exploratory analysis, and feature engineering have been finalized.

**Phase 2 (In Progress)**  
The next stage will involve building and evaluating predictive models (Logistic Regression and tree-based models) to estimate churn probability and identify high-risk customer segments.

---

This project is part of a structured banking analytics case study and demonstrates an end-to-end data preparation and exploratory analysis workflow.
