# Zomato Restaurant Business Analysis

![Python](https://img.shields.io/badge/Python-Data%20Analysis-blue)
![Pandas](https://img.shields.io/badge/Pandas-EDA-purple)
![SQL](https://img.shields.io/badge/SQL-Analysis-blue)
![SQLite](https://img.shields.io/badge/SQLite-SQL%20Engine-lightgrey)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange)
![Google%20Colab](https://img.shields.io/badge/Google%20Colab-Notebook-yellow)
![Status](https://img.shields.io/badge/Project-Completed-success)

## 📊 Project Overview

An end-to-end **Zomato Restaurant Business Analysis** case study combining **SQL, Python EDA and advanced business analysis** to understand restaurant performance, customer engagement, pricing, digital delivery adoption and city-level market opportunities.

The project is structured as a continuation of the original SQL case study. The advanced EDA notebook extends the analysis from individual business questions into a broader analytical framework:

**Data Understanding → Data Quality → SQL Business Analysis → Python EDA → Advanced Analysis → Segmentation → Market Opportunity → Business Insights → Recommendations**

The analysis covers:

- Restaurant pricing and price tiers
- Ratings and customer engagement
- Online delivery adoption
- Table booking and delivery availability
- Cuisine popularity
- Country and city restaurant distribution
- Restaurant performance segmentation
- Value-for-money analysis
- City-level market profiling
- Correlation analysis
- Premium vs value-oriented cities
- Project-defined Market Opportunity Score

---

## 🚀 Project Resources

### Google Colab

[▶ View Google Colab Notebook](https://colab.research.google.com/drive/1Xc73k_6tvUaSYy0BHkWq1IVnLd21QwYe?usp=sharing)

### GitHub

The repository contains the original SQL case study and the extended EDA & Advanced Analysis notebook.

---

# 🎯 Business Problem

The objective is to use restaurant-level data to answer practical business questions around **restaurant performance, customer behaviour, pricing and market opportunities**.

Key questions include:

- Which restaurants are the most expensive?
- Which restaurants offer strong value for money?
- Which restaurants have high ratings and strong customer engagement?
- Which cities have the highest online-delivery adoption?
- Which cities have the largest restaurant presence?
- Which restaurants offer delivery without table booking?
- Which cuisines receive the highest customer engagement?
- How do ratings, votes, pricing and delivery availability vary across restaurants?
- How does customer engagement differ across cities and restaurants?
- Which cities show different combinations of restaurant supply, demand, quality and delivery adoption?
- Which markets may represent opportunities based on a project-defined analytical score?

The goal is to demonstrate not only technical SQL/Python skills, but also the ability to convert analysis into **business-oriented insights and recommendations**.

---

# 📁 Dataset

The Zomato dataset contains **9,551 restaurant records across 18 columns**, covering multiple countries and cities.

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

# 🧩 Phase 1 – SQL Business Case Study

The original SQL analysis answers eight core business questions.

### Q1 – Most Expensive Restaurants

Identify the top 10 restaurants based on average cost for two people, along with their locations and price tiers.

### Q2 – Rating & Vote Data Quality

Identify restaurants with zero ratings, zero votes or null values in rating/vote fields.

### Q3 – Indian Restaurants Without Online Delivery

Identify Indian restaurants serving Indian cuisine that operate without online delivery.

### Q4 – High-Performing, Budget-Friendly Restaurants

Identify restaurants meeting all three criteria:

- Rating >= 4.5
- Votes > 500
- Average cost for two < ₹800

### Q5 – Online Delivery Adoption by City

Identify cities with at least 10 listed restaurants and rank them by online-delivery adoption percentage.

### Q6 – Delivery Without Table Booking

Identify cities with the highest number of restaurants that actively provide delivery but do not provide table booking.

### Q7 – Most Popular Cuisine by City

Identify the cuisine with the highest total customer votes in each city and determine the highest-voted city/cuisine combination.

### Q8 – City-Level Dining Cost

Identify cities whose average dining cost exceeds the overall average and examine the lowest-cost city.

---

# 🔎 Phase 2 – EDA & Advanced Analysis

The **Zomato EDA & Advanced Analysis** notebook extends the original SQL case study with additional analysis from **Q9 onward**.

[▶ View Google Colab Notebook](https://colab.research.google.com/drive/188SNmUxsUd7XcYs_fepqCU9sghCcTDLN?usp=sharing)

## Q9 – Dataset Overview

Establish the overall scale of the dataset by calculating:

- Total restaurants
- Total countries
- Total cities
- Total cuisine combinations

This provides the baseline for interpreting subsequent analysis.

## Q10–Q12 – Data Quality Analysis

The advanced notebook evaluates:

- Missing restaurant names, cities, cuisines, ratings, votes and cost values
- Zero-rating restaurants
- Zero-vote restaurants
- Restaurants with either zero rating or zero votes
- Duplicate Restaurant IDs

The analysis highlights why data-quality checks should be completed before calculating restaurant-level KPIs.

## Q13–Q14 – Restaurant Distribution

Explore restaurant supply across:

- Top countries by restaurant count
- Top cities by restaurant count

This helps identify where the dataset is concentrated and provides context for country- and city-level comparisons.

## Q15–Q16 – Rating & Pricing Analysis

Analyze:

- Restaurant rating bands
- Price range distribution in India
- Average rating by price range
- Average customer votes by price range
- Average cost by price range

This helps examine the relationship between restaurant pricing, customer engagement and ratings.

## Q17–Q18 – Online Delivery Analysis

Extend the delivery analysis by examining:

- Top cities by online-delivery adoption
- Online-delivery adoption across Indian price ranges

The analysis helps identify markets and price segments with different levels of digital-ordering adoption.

## Q19–Q20 – Customer Engagement Analysis

Measure customer engagement using recorded restaurant votes through:

- Top Indian cities by total votes
- Average votes by city
- Restaurant distribution across vote bands
- Average rating across engagement bands

Votes are treated as a **recorded engagement measure**, not as unique customers or orders.

## Q21 – Cuisine Analysis

Identify the cuisine combinations receiving the highest total customer votes and examine their average ratings.

This provides a basis for understanding cuisine-level customer engagement.

---

# 📈 Advanced Business Analysis

## Correlation Analysis

The notebook evaluates relationships between:

- `Rating`
- `Votes`
- `Average_Cost_for_two`
- `Price_range`

> Correlation measures association and does **not** establish causation.

---

## 🏷️ Restaurant Performance Segmentation

Restaurants in India are grouped into project-defined business segments using rating, votes and average cost.

### Segments

- **High Value Performer**
- **Strong Performer**
- **Average Performer**
- **Needs Attention**

The thresholds are explicitly defined within the project and are **not official Zomato classifications**.

The segmentation converts individual restaurant records into business-oriented groups that can be used for analysis of promotion, discovery and customer acquisition opportunities.

---

## 💰 Value-for-Money Analysis

The advanced analysis identifies restaurants that combine:

- Rating >= 4.5
- Votes > 500
- Average cost for two < 800

The analysis is intended to identify restaurants that demonstrate a combination of **strong customer response and relatively affordable pricing**.

---

## 🌆 City-Level Market Profile

The notebook creates a consolidated city-level view for Indian cities with at least 10 restaurants.

Metrics include:

- Restaurant count
- Average rating
- Average votes
- Average cost
- Delivery restaurant count
- Online-delivery percentage
- Total votes

This enables comparison of city markets across **supply, customer engagement, pricing, quality and digital adoption**.

---

# 🎯 Project-Defined Market Opportunity Score

The project introduces a **Market Opportunity Score** to make the city analysis more decision-oriented.

The score combines four components:

| Component | Weight |
|---|---:|
| Delivery Gap | **30%** |
| Customer Demand | **30%** |
| Restaurant Density | **20%** |
| Average Rating / Quality | **20%** |

The calculation uses normalized city-level metrics and produces a project-defined score for comparing markets.

> **Important:** The Market Opportunity Score is a portfolio analytical framework created specifically for this project. It is **not an official Zomato metric** and should not be treated as a validated commercial market-ranking model.

A higher score represents a combination of **restaurant supply, recorded customer engagement, restaurant quality and room for greater online-delivery adoption** within the project's analytical framework.

---

# 🍽️ Advanced SQL Analysis

The advanced notebook also demonstrates a window-function approach to identify the **most-voted cuisine in each city**.

The workflow uses:

1. City + cuisine aggregation
2. Total vote calculation
3. `ROW_NUMBER()` partitioned by city
4. Selection of the highest-voted cuisine per city

This demonstrates how SQL can move from simple aggregation to more advanced analytical patterns.

---

# 💎 Premium vs Value-Oriented Cities

The project additionally profiles Indian cities based on average dining cost.

### Premium-Oriented City Analysis

Cities are ranked by higher average dining cost while also displaying:

- Average rating
- Average votes
- Restaurant count

### Value-Oriented City Analysis

Cities are also examined from the lower-cost end using the same supporting metrics.

This creates a framework for comparing **premium-oriented and value-oriented restaurant markets** without treating cost alone as a measure of restaurant quality.

---

# 💡 Business Insights & Recommendations

The combined SQL and advanced EDA analysis supports several business-oriented observations:

### 1. Evaluate Delivery Expansion Opportunities

Cities with a meaningful restaurant base, customer engagement and lower online-delivery adoption can be investigated as potential areas for delivery expansion.

### 2. Promote Value-for-Money Restaurants

Restaurants combining strong ratings, meaningful customer engagement and relatively affordable pricing can be considered for value-focused discovery or promotional campaigns.

### 3. Personalize Cuisine Discovery

City-level cuisine popularity can support personalized cuisine discovery and city-specific recommendations.

### 4. Differentiate Premium and Value Markets

Higher-cost markets and lower-cost markets can be analyzed differently when designing restaurant discovery, pricing and delivery strategies.

### 5. Improve Customer Engagement

Restaurants with very limited recorded votes can be analyzed separately from highly engaged restaurants when evaluating performance.

### 6. Monitor Digital Delivery Adoption

Online-delivery adoption should be evaluated together with restaurant supply, pricing, customer engagement and ratings rather than as an isolated metric.

### 7. Maintain Strong Data Quality Controls

Missing values, duplicate IDs, zero-engagement records and unusual cost observations should be checked before calculating business KPIs.

---

# 🧮 Analytical Framework

```text
PHASE 1 – SQL BUSINESS CASE STUDY
│
├── Q1  Restaurant Pricing
├── Q2  Rating & Vote Data Quality
├── Q3  Indian Restaurants Without Online Delivery
├── Q4  High-Performing Budget-Friendly Restaurants
├── Q5  City-Level Delivery Adoption
├── Q6  Delivery Without Table Booking
├── Q7  Cuisine Popularity by City
└── Q8  City-Level Dining Cost

PHASE 2 – PYTHON EDA & ADVANCED ANALYSIS
│
├── Q9   Dataset Overview
├── Q10  Missing Value Analysis
├── Q11  Zero Rating & Vote Analysis
├── Q12  Duplicate Restaurant ID Check
├── Q13  Country Distribution
├── Q14  City Distribution
├── Q15  Rating Distribution
├── Q16  Price Range Analysis
├── Q17  City-Level Delivery Adoption
├── Q18  Delivery by Price Range
├── Q19  Customer Engagement by City
├── Q20  Vote Band Analysis
├── Q21  Cuisine Engagement Analysis
├── Correlation Analysis
├── Restaurant Segmentation
├── Value-for-Money Analysis
├── City Market Profile
├── Market Opportunity Score
├── Q26  Most Voted Cuisine by City
├── Q27  Premium-Oriented Cities
└── Q28  Value-Oriented Cities
```

### End-to-End Workflow

**Raw Dataset → Data Validation → SQL Business Questions → Python EDA → Advanced Analysis → Segmentation → Market Opportunity Analysis → Business Insights → Recommendations**

---

# 🛠️ Technology Stack

| Tool | Purpose |
|---|---|
| **Python** | Data analysis and EDA |
| **Pandas** | Data manipulation and analysis |
| **SQLite** | SQL analysis inside the Python notebook |
| **SQL** | Business-question analysis |
| **Matplotlib** | Data visualization |
| **Jupyter Notebook** | Notebook development |
| **Google Colab** | Cloud notebook execution and sharing |
| **GitHub** | Version control and portfolio presentation |

---

# 🧠 Skills Demonstrated

### SQL

- SELECT / WHERE / ORDER BY
- GROUP BY and HAVING
- Aggregations
- CASE statements
- Subqueries
- CTEs
- Window functions
- `ROW_NUMBER()`
- City and cuisine-level analysis

### Python & EDA

- Pandas
- Dataset profiling
- Data-quality validation
- Missing-value analysis
- Duplicate detection
- Distribution analysis
- Correlation analysis
- Data segmentation
- Business-oriented feature creation

### Business Analytics

- Restaurant performance analysis
- Customer engagement analysis
- Pricing analysis
- Delivery adoption analysis
- Cuisine analysis
- Geographic market analysis
- Value-for-money analysis
- Market opportunity framework
- Business insight generation
- Recommendation development

---

# 📂 Repository Structure

```text
Zomato Restaurant Business Analysis/
│
├── README.md
│
├── data/
│   └── Zomato.xlsx
│
├── notebooks/
│   ├── 01_Zomato_SQL_Case_Study.ipynb
│   └── 02_Zomato_Case_Study_Continuation_EDA_Advanced.ipynb
│
└── documentation/
    └── analysis_report.pdf
```

If the raw dataset is not included in the public repository, the `data/` folder can be retained as a reference to the source dataset used for the analysis.

---

# ⚠️ Analytical Limitations

1. The dataset is a snapshot and does not provide historical restaurant performance trends.
2. The dataset contains multiple countries and currencies, so direct global cost comparisons can be misleading without currency normalization.
3. India represents the majority of the dataset, so overall results are strongly influenced by the Indian restaurant market.
4. Votes represent recorded engagement and should not automatically be interpreted as unique customers or orders.
5. Correlation indicates association and does not establish causation.
6. Restaurant segmentation thresholds are project-defined analytical rules.
7. The Market Opportunity Score is a project-defined heuristic and has not been presented as an official Zomato metric.
8. City comparisons are restricted to markets meeting the analysis thresholds where specified, such as a minimum restaurant count of 10.
9. Business recommendations should be validated using current operational, financial and historical data before implementation.

---

# 📚 Portfolio Deliverables

- SQL business case study — Q1 to Q8
- Python EDA & Advanced Analysis — Q9 onward
- Dataset profiling
- Data-quality analysis
- Restaurant and city distribution analysis
- Rating and pricing analysis
- Online-delivery analysis
- Customer engagement analysis
- Cuisine analysis
- Correlation analysis
- Restaurant performance segmentation
- Value-for-money analysis
- City market profiling
- Project-defined Market Opportunity Score
- Premium vs value-oriented city analysis
- Advanced SQL using CTEs and window functions
- Business insights
- Business recommendations
- GitHub documentation
- Google Colab notebook

---

# 👤 Author

**Vijay Kumar**

Data Analytics | SQL | Python | Pandas | Business Analytics

---

## ⭐ Project Summary

This project demonstrates an end-to-end approach to restaurant market analytics using **SQL + Python + EDA + Advanced Analysis**.

Rather than stopping at individual SQL queries, the project progresses from **data validation and exploratory analysis to restaurant segmentation, city-level market profiling and a project-defined opportunity framework**.

**Understand → Validate → Analyze → Segment → Compare → Interpret → Recommend**
