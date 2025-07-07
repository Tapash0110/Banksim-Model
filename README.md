# Detecting Fraud in Banking Data – Summary

## 📊 Exploratory Data Analysis (EDA)

Initial EDA revealed the following insights:

1. **Class Imbalance**:  
   Only **1.21%** of the transactions were fraudulent, highlighting a strong class imbalance. This necessitates the use of:
   - Models robust to imbalanced data
   - Or synthetic data techniques (e.g., SMOTE, ADASYN)

2. **Fraudulent Transactions Involve Higher Amounts**:  
   Although frauds are fewer in number, they tend to involve **larger transaction amounts**.

3. **Risky Categories**:  
   Categories with the **most frequent frauds** include:
   - `es_sportsandtoys`
   - `es_health`
   - `es_wellnessandbeauty`

4. **Age Buckets**:  
   Fraud was most prevalent in age categories:
   - `2`
   - `3`

5. **Gender**:  
   Data indicated that **females were more involved** in fraud compared to males.

---

## 🧠 Dimensionality Reduction

Though dimensionality reduction was considered due to the high number of features, each component had a satisfactory level of **explained variance**. As a result, dimensionality reduction was **not pursued further**.

---

## 🎯 Classification Strategy & Metrics

In fraud detection:

- **Recall**: Measures how many actual frauds were correctly identified.  
  → Important for **catching all frauds**.

- **Precision**: Measures how many predicted frauds were truly fraudulent.  
  → Important for **avoiding unnecessary customer disruption**.

Hence, a balance between **Precision** and **Recall** is critical. Evaluation focused on:
- **Precision-Recall Curves (PR-AUC / AUC-PR)**
- **Type I & Type II Errors**

---

## 🏆 Model Evaluation

- **XGBoost with best parameters (via Grid Search)** was the top-performing model:
  - High **AUC**, **Precision**, and **Recall**
  - Lowest **Type II Error** (false negatives)

- While **Ensemble Learning** had the **lowest Type I Error** (false positives), the **priority is minimizing Type II Error** to avoid missing actual fraudulent transactions.

This aligns with the goal:  
> Predicting fraud in real-time with minimal missed frauds and reasonable accuracy.

