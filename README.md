# Zomato Restaurant Market Analysis

![Python](https://img.shields.io/badge/Python-Data%20Analysis-blue)
![Pandas](https://img.shields.io/badge/Pandas-EDA-purple)
![SQL](https://img.shields.io/badge/SQL-Analysis-blue)
![SQLite](https://img.shields.io/badge/SQLite-SQL%20Engine-lightgrey)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange)
![Google%20Colab](https://img.shields.io/badge/Google%20Colab-Notebook-yellow)
![Status](https://img.shields.io/badge/Project-Completed-success)

## 📊 Project Overview

An end-to-end **Zomato Restaurant Market Analytics** case study combining **SQL, Python EDA and advanced business analysis** to understand restaurant performance, customer engagement, pricing, online-delivery adoption and city-level market opportunities.

The project progresses from the original SQL case study into a deeper analytical workflow:

**Data Understanding → Data Validation → SQL Business Analysis → Python EDA → Advanced Analysis → Segmentation → Market Profiling → Opportunity Analysis → Business Insights → Recommendations**

### Analysis Areas

- Restaurant pricing and price tiers
- Ratings and customer engagement
- Data-quality validation
- Online-delivery adoption
- Customer engagement by city and vote band
- Cuisine-level engagement
- Correlation analysis
- Restaurant performance segmentation
- Value-for-money analysis
- Indian city market profiling
- Premium vs value-oriented cities
- Project-defined Market Opportunity Score

---

## 🚀 Project Resources

### Google Colab

[▶ View Google Colab Notebook](https://colab.research.google.com/drive/1Xc73k_6tvUaSYy0BHkWq1IVnLd21QwYe?usp=sharing)

[▶ View Google Colab Notebook](https://colab.research.google.com/drive/188SNmUxsUd7XcYs_fepqCU9sghCcTDLN?usp=sharing)

### Repository

The repository contains the original SQL case study and the final **EDA & Advanced Analysis** notebook.

---

# 🎯 Business Problem

The objective is to use restaurant-level data to answer practical business questions around:

- Restaurant performance
- Customer engagement
- Pricing
- Online-delivery adoption
- Cuisine preferences
- City-level market structure
- Value-for-money opportunities
- Market opportunity identification

The project focuses not only on producing SQL/Python outputs, but on **validating the data, questioning unexpected results and translating analysis into business-oriented insights**.

---

# 📁 Dataset

The Zomato dataset contains **9,551 restaurant records across 18 columns**.

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
| `Price_range` | Restaurant price category |
| `Votes` | Recorded customer votes |
| `Average_Cost_for_two` | Average cost for two people |
| `Rating` | Restaurant rating |

---

# 🔎 Key Analytical Decision: Validate Context Before Interpreting

One of the most important findings in the project came from **questioning the comparability of the data before interpreting the result**.

The dataset contains **15 countries and 12 currencies**. Therefore, raw `Average_Cost_for_two` values cannot be directly compared across countries without currency normalization.

India represents approximately **90.6% of the dataset**, making it the dominant market.

For cost-based and market-level analysis where a consistent currency and market are required, the final analysis therefore uses **India as the primary analytical context**.

This became particularly important in the correlation analysis.

### Correlation — All Countries

| Relationship | Correlation |
|---|---:|
| Rating ↔ Votes | **0.35** |
| Rating ↔ Average Cost | **0.06** |
| Rating ↔ Price Range | **0.46** |
| Votes ↔ Average Cost | **0.07** |
| Votes ↔ Price Range | **0.31** |
| Average Cost ↔ Price Range | **0.08** |

### Correlation — India Only

| Relationship | Correlation |
|---|---:|
| Rating ↔ Votes | **0.32** |
| Rating ↔ Average Cost | **0.36** |
| Rating ↔ Price Range | **0.43** |
| Votes ↔ Average Cost | **0.28** |
| Votes ↔ Price Range | **0.31** |
| Average Cost ↔ Price Range | **0.84** |

The change in the **Average Cost ↔ Price Range** relationship from **0.08 to 0.84** shows why analytical context matters.

> **Correlation shows association, not causation.**

The India-only analysis reveals a strong association between cost and price range within a consistent market/currency context. It does **not** establish that one variable causes the other.

---

# 🧩 Phase 1 – SQL Business Case Study

The original SQL case study answers eight core business questions.

### Q1 – Most Expensive Restaurants
Identify the top 10 restaurants based on average cost for two people, along with locations and price tiers.

### Q2 – Rating & Vote Data Quality
Identify restaurants with zero ratings, zero votes or null values in rating/vote fields.

### Q3 – Indian Restaurants Without Online Delivery
Identify Indian restaurants serving Indian cuisine that operate without online delivery.

### Q4 – High-Performing, Budget-Friendly Restaurants
Identify restaurants meeting:

- Rating >= 4.5
- Votes > 500
- Average cost for two < ₹800

### Q5 – Online Delivery Adoption by City
Identify qualifying cities and compare online-delivery adoption.

### Q6 – Delivery Without Table Booking
Identify cities with restaurants that actively provide delivery but do not provide table booking.

### Q7 – Most Popular Cuisine by City
Identify the cuisine with the highest total customer votes in each city.

### Q8 – City-Level Dining Cost
Identify cities whose average dining cost exceeds the overall average and examine lower-cost markets.

---

# 🔬 Phase 2 – Python EDA & Advanced Analysis

The final notebook extends the SQL case study from **Q9 onward**.

## Q9 – Dataset Overview

Establish the scale of the dataset:

- Total restaurants
- Total countries
- Total cities
- Total cuisine combinations

## Q10–Q12 – Data Quality Analysis

The final analysis checks:

- Missing restaurant names
- Missing cities
- Missing cuisines
- Missing ratings
- Missing votes
- Missing average cost
- Zero ratings
- Zero votes
- Duplicate Restaurant IDs

### Key Findings

- **9,551 rows**
- **9 missing cuisine values**
- No missing restaurant names, cities, ratings, votes or average-cost values
- **0 restaurants with zero rating**
- **1,094 restaurants with zero votes**
- **0 duplicate Restaurant IDs**

---

## Q13–Q14 – Restaurant Distribution

The analysis explores restaurant supply across countries and cities.

A key observation is that **India dominates the dataset with approximately 90.6% of restaurant records**.

Within India, **New Delhi has a very large concentration of restaurant records**, making it important to distinguish market size from customer engagement and quality.

---

## Q15–Q16 – Rating & Pricing Analysis

The analysis examines:

- Rating bands
- Price-range distribution in India
- Average rating by price range
- Average votes by price range
- Average cost by price range

Price Range 1 contains the largest number of restaurants, while higher price ranges generally show higher average ratings and engagement.

Average cost also increases substantially across price ranges within India.

---

## Q17–Q18 – Online Delivery Analysis

Online-delivery adoption is examined:

- By Indian city
- By Indian price range

Qualifying cities have:

- At least **10 restaurants**
- At least **1 restaurant offering online delivery**

### Key Findings

**Chennai records the highest online-delivery adoption among the qualifying Indian cities at 65%.**

Online-delivery adoption by price range:

| Price Range | Delivery Adoption |
|---|---:|
| Price Range 2 | **44.82%** |
| Price Range 3 | **35.82%** |
| Price Range 1 | **16.32%** |
| Price Range 4 | **11.08%** |

This indicates that delivery adoption is strongest among the mid-priced segments in this dataset.

---

## Q19–Q20 – Customer Engagement Analysis

Customer engagement is evaluated using recorded restaurant votes.

### City-Level Engagement

New Delhi has the highest total votes because of its very large restaurant base.

However, smaller markets such as Bangalore, Kolkata, Chennai and Hyderabad show much higher average votes per restaurant and higher average ratings.

This demonstrates why **total engagement and engagement per restaurant can tell different stories**.

### Vote Bands

| Vote Band | Average Rating |
|---|---:|
| 1–99 votes | **2.74** |
| 100–499 votes | **3.64** |
| 500–999 votes | **3.94** |
| 1,000+ votes | **4.11** |

Votes are treated as **recorded engagement**, not as unique customers or orders.

---

## Q21 – Cuisine Engagement Analysis

Cuisine combinations are ranked using total recorded customer votes.

This can support:

- Cuisine-focused discovery
- City-specific recommendations
- Cuisine-level promotional opportunities

---

# 📈 Advanced Business Analysis

## Correlation Analysis

The notebook evaluates relationships between:

- `Rating`
- `Votes`
- `Average_Cost_for_two`
- `Price_range`

The analysis is performed first on the complete dataset and then repeated for **India only** after identifying the currency comparability issue.

### Analytical lesson

**A technically correct calculation can still lead to a misleading business interpretation if the underlying variables are not comparable.**

The workflow becomes:

**Unexpected Result → Question the Data → Check Context → Filter → Reanalyse → Interpret**

---

# 🏷️ Restaurant Performance Segmentation

Restaurants in India are grouped into four project-defined segments using rating, votes and average cost.

### Segments

- **High Value Performer**
- **Strong Performer**
- **Average Performer**
- **Needs Attention**

The thresholds are explicitly defined within the project and are **not official Zomato classifications**.

### Segment Summary

| Segment | Restaurants | Avg Rating | Avg Votes | Avg Cost |
|---|---:|---:|---:|---:|
| Average Performer | **4,581** | 3.46 | 131 | 713.63 |
| Needs Attention | **3,562** | 1.68 | 19 | 417.77 |
| Strong Performer | **497** | 4.25 | 1,019 | 1,269.01 |
| High Value Performer | **12** | 4.65 | 1,102 | 458.33 |

Most restaurants fall into the **Average Performer** or **Needs Attention** segments, while only a small number combine strong ratings, customer engagement and relatively low cost.

---

# 💰 Value-for-Money Analysis

The project identifies restaurants that combine:

- Rating >= 4.5
- Votes > 500
- Average cost for two < ₹800

This identifies restaurants that demonstrate a combination of **strong customer response and relatively affordable pricing** within the Indian market.

---

# 🌆 Indian City Market Profile

The city-level profile combines:

- Restaurant count
- Average rating
- Average votes
- Average cost
- Delivery restaurant count
- Online-delivery percentage
- Total votes

The analysis uses Indian cities meeting the defined restaurant-count and delivery-adoption criteria.

### Key Observation

**A large restaurant market does not automatically mean stronger ratings or customer engagement.**

New Delhi has a very large restaurant base and the highest total votes, while smaller markets such as Bangalore, Kolkata, Chennai and Hyderabad show substantially higher average ratings and average votes per restaurant.

---

# 🎯 Project-Defined Market Opportunity Score

The project creates a **Market Opportunity Score** to make the city analysis more decision-oriented.

The score combines four normalized components:

| Component | Weight |
|---|---:|
| Delivery Gap | **30%** |
| Customer Demand | **30%** |
| Restaurant Density | **20%** |
| Average Rating / Quality | **20%** |

> **Important:** This is a portfolio-defined analytical framework. It is **not an official Zomato metric** and should not be treated as a validated commercial market-ranking model.

### Final Market Opportunity Scores

| City | Score |
|---|---:|
| **Bangalore** | **69.51** |
| **Kolkata** | **60.56** |
| **Mumbai** | **52.41** |
| **Hyderabad** | **52.14** |
| **Pune** | **48.90** |
| **New Delhi** | **46.87** |
| **Chennai** | **44.51** |
| **Kochi** | **43.27** |
| **Chandigarh** | **42.80** |
| **Coimbatore** | **39.13** |

The score is designed to combine restaurant supply, recorded customer demand, quality and room for greater online-delivery adoption within the project's analytical framework.

---

# 🍽️ Advanced SQL – Most Popular Cuisine in Each City

The project uses SQL window functions to identify the most-voted cuisine in each city.

### Workflow

1. Aggregate votes by city and cuisine
2. Calculate total votes
3. Apply `ROW_NUMBER()` partitioned by city
4. Select the highest-voted cuisine

This demonstrates progression from basic aggregation to advanced analytical SQL.

---

# 💎 Premium vs Value-Oriented Cities

Indian cities are also profiled by average dining cost.

### Premium-Oriented Cities

Cities are examined using higher average cost alongside:

- Average rating
- Average votes
- Restaurant count

### Value-Oriented Cities

Cities are examined from the lower-cost end using the same supporting metrics.

The purpose is to distinguish **premium-oriented and value-oriented markets** without treating cost alone as a measure of restaurant quality.

---

# 💡 Business Insights & Recommendations

### 1. Evaluate Delivery Expansion Opportunities

Markets with meaningful restaurant supply, customer engagement and lower delivery adoption can be investigated as potential areas for expansion.

### 2. Promote Value-for-Money Restaurants

Restaurants combining strong ratings, meaningful engagement and relatively affordable pricing can be considered for value-focused discovery and promotional campaigns.

### 3. Personalize Cuisine Discovery

City-level cuisine engagement can support personalized cuisine discovery and city-specific recommendations.

### 4. Differentiate Premium and Value Markets

Premium-oriented and value-oriented markets can be approached differently when designing restaurant discovery, pricing and delivery strategies.

### 5. Improve Customer Engagement

Restaurants with limited recorded votes can be analyzed separately from highly engaged restaurants when evaluating performance.

### 6. Monitor Digital Delivery Adoption

Online-delivery adoption should be evaluated alongside restaurant supply, pricing, engagement and ratings rather than as an isolated metric.

### 7. Maintain Strong Data Quality Controls

Unexpected results should trigger checks on:

- Currency
- Geography
- Data comparability
- Missing values
- Duplicate IDs
- Zero-engagement records
- Outliers and unusual observations

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

**Raw Dataset → Data Validation → SQL Business Questions → Python EDA → Context Validation → Advanced Analysis → Segmentation → Market Profiling → Opportunity Analysis → Business Insights → Recommendations**

---

# 🛠️ Technology Stack

| Tool | Purpose |
|---|---|
| **Python** | Data analysis and EDA |
| **Pandas** | Data manipulation and analysis |
| **SQLite** | SQL analysis inside the Python notebook |
| **SQL** | Business-question analysis |
| **Matplotlib** | Data visualization |
| **Seaborn** | Correlation heatmaps |
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
- Visualization

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
- Analytical context validation

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
│   └── 02_Zomato_Case_Study_Continuation_EDA_Advanced.ipynb
│
└── documentation/
    └── analysis_report.pdf
```

If the raw dataset is not included in the public repository, the `data/` folder can be retained as a reference to the source dataset used for the analysis.

---

# ⚠️ Analytical Limitations

1. The dataset contains multiple countries and currencies, so global cost comparisons should not be made without currency normalization.
2. The dataset is a snapshot and does not show changes over time.
3. India represents the majority of the dataset, so overall results are strongly influenced by the Indian restaurant market.
4. Votes represent recorded engagement and should not automatically be treated as unique customers or orders.
5. Correlation indicates association and does not establish causation.
6. Restaurant segmentation thresholds are project-defined analytical rules.
7. The Market Opportunity Score is a project-defined heuristic and is not an official Zomato metric.
8. City-level comparisons use minimum restaurant-count and positive-delivery-adoption filters where specified.
9. The analysis does not establish causal relationships between pricing, ratings, votes or delivery adoption.
10. Business recommendations should be validated using current operational, financial and historical data before implementation.

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
- Correlation analysis with context validation
- Restaurant performance segmentation
- Value-for-money analysis
- Indian city market profiling
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

The analysis does not stop at producing numbers. It moves from **data validation and exploratory analysis to questioning unexpected results, controlling analytical context, segmentation, city-level market profiling and a project-defined opportunity framework**.

**Understand → Validate → Question → Analyse → Segment → Compare → Interpret → Recommend**
