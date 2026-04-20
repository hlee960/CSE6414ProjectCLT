# 📊 Customer Segmentation & CLV Prediction (CSE6414 Project)

## Project Overview
This project builds a full customer analytics pipeline using the Online Retail II dataset.

The goal is to move beyond descriptive analytics and develop a data-driven framework for:
- Time-based hold-out to predict 6-month CLV
- Customer segmentation
- Customer lifetime value (CLV) prediction
- Business-driven insights for retention and growth strategies

---

## Dataset
- Source: UCI Online Retail II Dataset
- Time Range: 2009 – 2011
- ~1.1M raw transactions → ~800K after cleaning, ~5,800 customers
---

## Methodology

### 1. Data Cleaning & Preprocessing
- ~800K cleaned transactions, ~5,800 customers
- Removed cancelled transactions
- Filtered invalid values (negative quantity/price)
- Handled missing customer IDs
- Outlier capping (99th percentile)

---

### 2. Feature Engineering (RFM)
- Recency
- Frequency
- Monetary

---

### 3. Customer Segmentation (K-Means)
- Optimal clusters selected using:
  - Elbow Method
  - Silhouette Score
- Final choice: **k = 4**

Segments:
- High-Value Loyalists
- Active Mid-Tier
- Occasional Buyers
- At-Risk / Dormant

---

### 4. CLV Modeling (Probabilistic)
- BG/NBD → purchase frequency
- Gamma-Gamma → monetary value
- Predicted 6-month CLV

---

### 5. Machine Learning CLV (XGBoost)
- Features:
  - frequency
  - recency
  - T (customer age)
  - monetary_value
- Performance:
  - R² ≈ 0.843 (strong predictive performance)

---

## Key Insights

- Customer value distribution follows a long-tail pattern (Pareto principle)
- High-value customers contribute disproportionately to revenue
- Frequency and monetary value are the strongest drivers of CLV
- Segmentation enables targeted marketing strategies:
  - Retention for high-value customers
  - Upselling for mid-tier
  - Reactivation for inactive users

---

## Key Contribution

- Unified framework combining:
  - Probabilistic CLV modeling (BG/NBD + Gamma-Gamma)
  - Machine learning (XGBoost)
- Bridges segmentation and prediction into a single pipeline

--- 

## Business Impact

This pipeline demonstrates how data can be used to:
- Personalize marketing strategies
- Improve customer retention
- Predict future revenue at the customer level

---

## Tech Stack
- Python
- Pandas / NumPy
- Scikit-learn
- Lifetimes (BG/NBD, Gamma-Gamma)
- XGBoost
- Matplotlib / Seaborn

---

## Future Improvements
- Incorporate time-series features
- Add deep learning-based segmentation
- Deploy as a real-time scoring system
