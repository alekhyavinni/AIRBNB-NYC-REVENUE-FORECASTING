# AIRBNB-NYC-REVENUE-FORECASTING
A machine learning project aimed at optimizing pricing strategies and identifying high-revenue property listings on Airbnb in New York City. Combines geospatial analytics, NLP, and tree-based modeling to deliver actionable insights for hosts navigating evolving city regulations.

# 🏙️ NYC Airbnb Price Classification Project

## 📌 Project Overview

This project explores Airbnb listings in New York City using the publicly available [Airbnb Open Data](https://www.kaggle.com/datasets/arianazmoudeh/airbnbopendata). The primary objective is to provide **actionable insights** for hosts by predicting whether a listing is **high-priced (Class 1)** or **low-priced (Class 0)** per night.

Due to poor regression model performance, the problem was reframed as a **binary classification** task. After extensive feature engineering and evaluation, a **Random Forest Classifier** was identified as the most effective model with an AUC of **0.80** and precision of **0.69**, making it highly useful for Airbnb hosts to prioritize listing optimization strategies.

---

## 👩‍💻 Authors

- Alekhya Erikipati  
- Yihua Chen  
- Christine Tang  
- Narotam Dhaliwal  
- Pui Ching Queenie Sung  
 ---

## 📂 File Structure

| File | Description |
|------|-------------|
| `V13_Airbnb_analysis_FINAL.ipynb` | Jupyter Notebook containing all code, EDA, cleaning, feature engineering, and model development. |
| `NYC_AirBnb_Project Report.pdf` | Comprehensive project report with business insights, model results, and appendices. |

---

## 📊 Problem Statement

Predict whether an Airbnb listing in NYC falls into a **high** or **low** daily price category using structured and unstructured data, including:

- Listing metadata (room type, location, availability)
- Host behavior (reviews, verification)
- Textual rules (amenities, house_rules)
- Proximity to NYC landmarks (via Google Maps API)

---

## 🧪 Approach

### 1. Data Cleaning & Preprocessing
- Removed duplicates and irrelevant columns (e.g., `license`)
- Converted monetary columns (e.g., `price`, `service_fee`) to numeric
- Handled outliers and missing data
- Standardized column naming

### 2. Feature Engineering
- NLP features from `house_rules` (e.g., sentiment, keyword presence)
- Created `proximity_score` to NYC attractions using Google Maps API
- Seasonality features from `last_review`
- One-hot encoding of categorical features

### 3. Model Development
- Attempted Regression → poor performance (Adj R² ≈ 0, high RMSE)
- Switched to Classification:
  - Binary: Class 0 (low-priced), Class 1 (high-priced)
  - Multi-class: 3 bins based on price
- Models tested: Logistic Regression, KNN, Random Forest, Gradient Boosting, XGBoost, LightGBM

### 4. Model Evaluation
- Metrics: Precision (primary), Recall, Mean CV Precision
- Best Model: **Random Forest Classifier**
  - Precision: **0.69**
  - ROC AUC: **0.80**

---

## 💡 Key Insights for Airbnb Hosts

- ✅ **Proximity to NYC attractions** significantly boosts price potential  
- ✅ Listings with **recent reviews**, **positive sentiment**, and **friendly rules** perform better  
- ❌ Avoid **private rooms**, **strict cancellation policies**, or outdated/inactive listings  
- Use NLP and data-driven optimization to improve listing descriptions and guest experience  

---

## 📈 Recommended Next Steps

- Automate proximity scoring for real-time new listings
- Use live Airbnb API (if accessible) for up-to-date data
- Expand model to include booking rate, guest count, and host revenue
- Consider deploying this as a dashboard for Airbnb hosts

---

## 📚 References

- [Kaggle Airbnb NYC Open Data](https://www.kaggle.com/datasets/arianazmoudeh/airbnbopendata)  
- Kolomatsky, M. (2021). *What Happened to Airbnb during the Pandemic?* NYTimes  
- Lung, N. (2023). *NYC Airbnb Regulations Overview*. Bloomberg

---

## 🛠️ Tech Stack

- Python (Pandas, NumPy, Scikit-learn)
- NLP (TextBlob, CountVectorizer)
- Google Maps API (for distance features)
- Matplotlib & Seaborn (visualization)
- Jupyter Notebook

---

## 📌 License

This project is academic and educational in nature. Not intended for commercial redistribution. All external data sources are publicly available and cited.

---
