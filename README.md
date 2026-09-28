# Zomato Restaurant Analytics

![Python](https://img.shields.io/badge/Python-Data%20Analysis-blue)
![Pandas](https://img.shields.io/badge/Pandas-EDA-purple)
![SQL](https://img.shields.io/badge/SQL-Analysis-blue)
![SQLite](https://img.shields.io/badge/SQLite-SQL%20Engine-lightgrey)
![Status](https://img.shields.io/badge/Project-Completed-success)

## 📊 Project Overview

An end-to-end **Restaurant Market Analytics** case study based on the Zomato restaurant dataset.

The project combines **SQL analysis and Python Exploratory Data Analysis (EDA)** to transform restaurant-level data into business-focused insights across:

- Restaurant pricing
- Ratings and customer engagement
- Online delivery adoption
- Table booking
- Cuisine preferences
- City-level restaurant markets
- Value-for-money restaurants
- Restaurant performance segmentation
- Market opportunity analysis

The project goes beyond isolated SQL queries by connecting:

**Data Understanding → Data Quality → SQL Business Analysis → Python EDA → Advanced Analysis → Business Insights → Recommendations**

---

## 🚀 Project Resources

### [▶ View Google Colab Notebook](https://colab.research.google.com/drive/1Xc73k_6tvUaSYy0BHkWq1IVnLd21QwYe?usp=sharing)


## 🎯 Business Problem

The analysis is designed to answer practical business questions such as:

- Which restaurants are the most expensive?
- Which restaurants offer strong value for money?
- Which restaurants have high ratings and strong customer engagement?
- Which cities have the highest online-delivery adoption?
- Which cities have the largest restaurant presence?
- Which restaurants offer delivery without table booking?
- Which cuisines receive the highest customer engagement?
- How do ratings, votes, pricing and delivery availability vary across restaurants?
- Which cities have relatively higher or lower dining costs?
- Which restaurant groups and markets may represent business opportunities?

The objective is to demonstrate how restaurant data can be converted into **clear business insights and actionable recommendations**.

---

# 📁 Dataset

The dataset contains **9,551 restaurant records across 18 columns**.

| Metric | Value |
|---|---:|
| Restaurant Records | **9,551** |
| Columns | **18** |
| Countries | **15** |
| Cities | **141** |
| Currencies | **12** |

### Core Columns

| Column | Description |
|---|---|
| `RestaurantID` | Restaurant identifier |
| `RestaurantName` | Restaurant name |
| `CountryCode` | Country code |
| `CountryName` | Country |
| `City` | City |
| `Address` | Restaurant address |
| `Locality` | Restaurant locality |
| `LocalityVerbose` | Detailed locality |
| `Cuisines` | Cuisine type(s) |
| `Currency` | Currency used for restaurant cost |
| `Has_Table_booking` | Table booking availability |
| `Has_Online_delivery` | Online delivery availability |
| `Is_delivering_now` | Current delivery availability |
| `Switch_to_order_menu` | Order-menu availability |
| `Price_range` | Restaurant price category |
| `Votes` | Customer votes |
| `Average_Cost_for_two` | Average cost for two people |
| `Rating` | Restaurant rating |

---

# 🧩 Data Quality & Analytical Considerations

Data quality was evaluated before the business analysis.

### Key checks

- Dataset structure and data types
- Missing values
- Duplicate records
- Zero ratings
- Zero votes
- Low-engagement restaurants
- Distribution of ratings and votes
- Cost outliers
- Currency consistency

### Key Findings

- **9,551 records** are present.
- No duplicate rows were identified.
- No missing or zero ratings were identified in the current dataset.
- **1,094 restaurants have zero votes.**
- **2,148 restaurants have Rating <= 1.0 and Votes <= 3.**
- Votes are highly skewed, with a median of approximately **31** compared with a mean of approximately **157**.
- `Average_Cost_for_two` contains significant high-value observations.

### Currency Consideration

`Average_Cost_for_two` is reported in different currencies across countries.

Therefore, direct international cost comparisons can be misleading.

Cost-based analysis should be performed within the same country/currency or after conversion to a common currency.

---

# 📌 SQL Business Case Study

The original SQL case study focuses on eight core business questions.

### Q1 – Most Expensive Restaurants

Identify the top 10 restaurants based on average cost for two people, along with city and price range.

### Q2 – Rating & Vote Data Quality

Identify restaurants with zero ratings, zero votes or null values in these fields.

### Q3 – Indian Restaurants Without Online Delivery

Identify Indian restaurants serving Indian cuisine that operate without online delivery.

### Q4 – High-Performing, Budget-Friendly Restaurants

Identify restaurants meeting:

- Rating >= 4.5
- Votes > 500
- Average cost for two < ₹800

### Q5 – Online Delivery Adoption by City

Identify cities with at least 10 restaurants and rank them by the percentage of restaurants offering online delivery.

### Q6 – Delivery Without Table Booking

Identify the top cities with the highest number of restaurants that offer delivery but do not provide table booking.

### Q7 – Most Popular Cuisine by City

For each city, identify the cuisine with the highest total customer votes and determine the highest-voted city-cuisine combination.

### Q8 – City-Level Dining Cost

Identify cities where average dining cost is above the overall average and determine the city with the lowest average cost.

---

# 🔎 Python Exploratory Data Analysis

The Python continuation extends the original SQL case study with:

1. Dataset profiling
2. Data quality analysis
3. Country distribution
4. City distribution
5. Rating distribution
6. Price-range analysis
7. Online-delivery adoption
8. Customer engagement
9. Cuisine analysis
10. Correlation analysis
11. Restaurant segmentation
12. Value-for-money analysis
13. City market profiling
14. Market opportunity analysis

---

# 📈 Key Business Findings

## 1. India Dominates the Dataset

India represents approximately **90.59% of all restaurant records**.

**Business implication:** Overall dataset-level results are heavily influenced by the Indian restaurant market.

## 2. Customer Engagement is Highly Concentrated

| Metric | Value |
|---|---:|
| Mean Votes | **156.91** |
| Median Votes | **31** |
| Maximum Votes | **10,934** |

The large difference between mean and median indicates that customer engagement is concentrated among a smaller group of restaurants.

## 3. Zero-Vote Restaurants

**1,094 restaurants have zero votes.**

These restaurants have no recorded customer voting activity and may require additional visibility or customer-engagement initiatives.

## 4. Low-Engagement, Low-Rating Restaurants

**2,148 restaurants have Rating <= 1.0 and Votes <= 3.**

This group should be treated separately when evaluating restaurant performance because customer engagement is extremely low.

## 5. Ratings Show Wide Variation

Ratings range from **1.0 to 4.9**, with a median of approximately **3.2**.

## 6. Restaurant Cost Requires Careful Interpretation

`Average_Cost_for_two` contains multiple currencies and significant high-value observations.

Country-level or currency-normalized analysis is therefore more appropriate than directly comparing all restaurants globally.

---

# 🧠 Advanced Analysis

## Restaurant Performance Segmentation

Restaurants are grouped using project-defined criteria based on:

- Rating
- Votes
- Average cost

Example segments:

- **High Value Performer**
- **Strong Performer**
- **Average Performer**
- **Needs Attention**

> These are analytical categories created for this project and are not official Zomato classifications.

## 💰 Value-for-Money Analysis

The analysis identifies restaurants combining:

- High ratings
- Strong customer engagement
- Relatively affordable cost

## 🌍 City Market Profile

Cities are compared using:

- Restaurant count
- Average rating
- Average votes
- Total votes
- Average cost
- Online-delivery adoption

## 🎯 Market Opportunity Score

A project-defined **Market Opportunity Score** combines:

- Delivery gap
- Customer demand
- Restaurant density
- Average rating

This is a portfolio analytical framework and **not an official Zomato metric**.

---

# 💡 Business Recommendations

### 1. Prioritize High-Opportunity Markets

Cities with strong restaurant supply and customer engagement but comparatively lower online-delivery adoption can be investigated for potential delivery expansion.

### 2. Promote Value-for-Money Restaurants

Highly rated restaurants with strong customer engagement and affordable pricing can be highlighted through value-focused discovery and promotional campaigns.

### 3. Personalize Cuisine Discovery

City-level cuisine popularity can support restaurant recommendations, search ranking and cuisine-specific promotions.

### 4. Differentiate Premium and Value Markets

Higher-cost markets can focus on premium dining experiences, while value-oriented markets can focus on affordability and delivery.

### 5. Improve Customer Engagement

Restaurants with very low or zero votes may benefit from stronger visibility and customer-engagement initiatives.

### 6. Monitor Online Delivery Adoption

Delivery adoption should be tracked alongside restaurant density, ratings and customer engagement.

### 7. Strengthen Data Quality Controls

Low-engagement records, missing values and extreme cost observations should be identified before calculating business KPIs.

---

# 🧮 SQL Analysis Framework

```text
01 – Data Understanding & Data Quality
02 – Restaurant Pricing
03 – Rating & Customer Engagement
04 – Online Delivery
05 – Table Booking & Delivery
06 – Cuisine Analysis
07 – City-Level Analysis
08 – Python EDA
09 – Restaurant Segmentation
10 – Market Opportunity Analysis
11 – Business Insights
12 – Business Recommendations
```

### Analytical Workflow

**Raw Dataset → Data Validation → SQL Analysis → Python EDA → Advanced Analysis → Business Insights → Recommendations**

---

# 🛠️ Technology Stack

| Tool | Purpose |
|---|---|
| **Python** | Data analysis and EDA |
| **Pandas** | Data manipulation and analysis |
| **SQLite** | SQL analysis within the Python notebook |
| **SQL** | Business-question analysis |
| **Matplotlib** | Data visualization |
| **Jupyter Notebook / Google Colab** | Development and presentation |
| **GitHub** | Version control and portfolio presentation |

---

# 🧠 Skills Demonstrated

- Python
- Pandas
- SQL
- SQLite
- Data profiling
- Data quality validation
- Missing-value analysis
- Duplicate detection
- Aggregation
- Filtering
- Grouping
- Subqueries
- CTEs
- Window functions
- Customer engagement analysis
- Restaurant segmentation
- Pricing analysis
- Geographic analysis
- Delivery analysis
- EDA
- Business storytelling
- Business recommendations

---

# 📂 Repository Structure

```text
zomato-restaurant-analytics/
│
├── README.md
│
├── data/
│   └── Zomato.xlsx
│
├── notebooks/
│   ├── 01_Zomato_SQL_Case_Study.ipynb
│   └── 02_Zomato_Python_EDA.ipynb
│
└── documentation/
    └── analysis_report.pdf
```

> If the raw dataset is not included in GitHub, keep the `data/` section as a reference to the source dataset used for the analysis.

---

# ⚠️ Analytical Limitations

1. The dataset is a snapshot and does not provide historical restaurant performance trends.
2. India represents the majority of the dataset.
3. `Average_Cost_for_two` contains multiple currencies.
4. Votes represent recorded engagement and should not automatically be interpreted as unique customers or orders.
5. Correlation indicates association and does not establish causation.
6. Restaurant segmentation thresholds are project-defined analytical rules.
7. The Market Opportunity Score is a project-defined heuristic.
8. Cost-based international comparisons require currency normalization.
9. Business recommendations should be validated with operational, financial and historical data before implementation.

---

# 📚 Portfolio Deliverables

- SQL business case study
- Python EDA notebook
- Data quality analysis
- Restaurant pricing analysis
- Customer engagement analysis
- Online delivery analysis
- Cuisine analysis
- City-level analysis
- Restaurant segmentation
- Market Opportunity Score
- Business insights
- Business recommendations
- GitHub documentation

---

# 👤 Author

**Vijay Kumar**

Data Analytics | SQL | Python | Pandas | Business Analytics

---

## ⭐ Project Summary

This portfolio project demonstrates how restaurant data can be transformed into business insights using:

**SQL + Python + EDA + Business Analysis**

The focus is not only on writing queries, but on demonstrating the complete analytical process:

**Understand the Data → Validate the Data → Ask Business Questions → Analyze → Interpret → Recommend**
