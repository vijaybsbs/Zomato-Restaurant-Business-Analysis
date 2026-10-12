# Zomato Restaurant Market Analysis

![Python](https://img.shields.io/badge/Python-Data%20Analysis-blue)
![Pandas](https://img.shields.io/badge/Pandas-EDA-purple)
![SQL](https://img.shields.io/badge/SQL-Analysis-blue)
![SQLite](https://img.shields.io/badge/SQLite-SQL%20Engine-lightgrey)
![Power BI](https://img.shields.io/badge/Power%20BI-Dashboard-yellow)
![DAX](https://img.shields.io/badge/DAX-Measures-orange)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange)
![Google%20Colab](https://img.shields.io/badge/Google%20Colab-Notebook-yellow)
![Status](https://img.shields.io/badge/Project-Completed-success)

## 📊 Project Overview

An end-to-end **Zomato Restaurant Market Analytics** case study built in three phases — **SQL → Python EDA → Python data cleaning + Power BI dashboard** — to understand restaurant performance, customer engagement, pricing and online-delivery adoption in India.

Each phase revisits the same data with a sharper lens. Phase 3 found two data-quality issues that changed several Phase 2 conclusions; those corrections are documented openly in [What Changed in Phase 3](#-what-changed-in-phase-3).

**Data Understanding → Validation → SQL Business Questions → Python EDA → Deeper Data Cleaning → Corrected Analysis → Power BI Dashboard → Business Insights**

---

## 🚀 Project Resources

| Resource | Link |
|---|---|
| Phase 1 – SQL Case Study (Colab) | [▶ Open notebook](https://colab.research.google.com/drive/1Xc73k_6tvUaSYy0BHkWq1IVnLd21QwYe?usp=sharing) |
| Phase 2 – Python EDA & Advanced Analysis (Colab) | [▶ Open notebook](https://colab.research.google.com/drive/188SNmUxsUd7XcYs_fepqCU9sghCcTDLN?usp=sharing) |
| Phase 3 – Data Cleaning Notebook | [`notebooks/zomato_eda.ipynb`](notebooks/zomato_eda.ipynb) |
| Phase 3 – Dashboard (PDF, 6 pages) | [`Powerbi/Zomato Powerbi - pdf.pdf`](Powerbi/Zomato%20Powerbi%20-%20pdf.pdf) |
| Phase 3 – Power BI file | [`Powerbi/Zomato.pbix`](Powerbi/Zomato.pbix) |

---

# 🎯 Business Problem

The objective is to use restaurant-level data to answer practical business questions around restaurant performance, customer engagement, pricing, online-delivery adoption, cuisine preferences and city-level market structure.

The project focuses not only on producing outputs, but on **validating the data, questioning unexpected results and correcting conclusions when the data does not support them**.

---

# 📁 Dataset

| Metric | Value |
|---|---:|
| Restaurant Records | **9,551** |
| Columns | **18** |
| Countries | **15** |
| Cities | **141** |
| Currency labels | **12** |
| India share of records | **90.6%** |

### Core Columns

| Column | Description |
|---|---|
| `RestaurantID` | Restaurant identifier |
| `RestaurantName` | Restaurant name |
| `CountryCode` / `CountryName` | Country |
| `City`, `Locality`, `LocalityVerbose`, `Address` | Location |
| `Cuisines` | Cuisine type(s), pipe-separated |
| `Currency` | Currency used for restaurant cost |
| `Has_Table_booking` | Table booking availability |
| `Has_Online_delivery` | Online delivery availability |
| `Is_delivering_now` | Delivery status at the time of extraction |
| `Switch_to_order_menu` | Order-menu flag |
| `Price_range` | Restaurant price category (1–4) |
| `Votes` | Recorded customer votes |
| `Average_Cost_for_two` | Average cost for two people |
| `Rating` | Restaurant rating |

---

# 🔁 What Changed in Phase 3

Phase 3 rebuilt the analysis from a cleaned dataset and found two issues that earlier phases had not caught:

1. **Rating 1.0 is a placeholder, not a low rating.** Every restaurant with fewer than 4 votes (2,139 in India) was given a rating of 1.0. These restaurants are *not rated yet*.
2. **Most non-NCR cities are capped at about 20 listings.** 28 Indian cities — including Mumbai, Bangalore, Chennai and Kolkata — have exactly 20 restaurants each. Their data is a sample, not the market.

| Earlier finding | Corrected finding | Status |
|---|---|---|
| 2,148 restaurants have *low ratings* and low engagement | They have fewer than 4 votes and carry a 1.0 placeholder — they are **not rated yet** | Reinterpreted |
| India average rating (raw): **2.77** | Excluding placeholders: **3.35** | Corrected |
| Avg rating by price range: **2.33 → 3.66** | **3.20 → 3.31 → 3.68 → 3.74** (flattens after Premium) | Corrected |
| Vote band 1–99 votes → avg rating **2.74** | Band included placeholder ratings for 1–3 votes; valid only for 4+ votes | Caveated |
| New Delhi avg rating **2.70**; Bangalore 4.38, Hyderabad 4.34, Chennai 4.31 | New Delhi: **3.30**. Small cities are capped at ~20 listings, likely popular restaurants — **not comparable** with New Delhi's full list | Conclusion withdrawn |
| "Smaller markets show stronger engagement per restaurant" (Bangalore 2,806 avg votes) | Same cause — sampling, not market behaviour | Conclusion withdrawn |
| Rating-based correlations (Rating ↔ Votes / Cost / Price range) | Calculated with placeholder ratings included; replaced by group comparisons on cleaned data | Superseded |
| Segment "Needs Attention" (3,562 restaurants, avg rating 1.68) | Avg rating driven mostly by 1.0 placeholders | Caveated |
| Market Opportunity Score: Bangalore #1 (69.51) | Quality and demand scores came from 20-listing samples and placeholder ratings | **Retired** — replaced by locality-level opportunity view within Delhi NCR |
| Average Cost ↔ Price Range: **0.08 → 0.84** (global → India) | Unaffected (no rating involved) | ✅ Still valid |
| Delivery adoption by price range (16% / 45% / 36% / 11%) | Unaffected | ✅ Still valid |

---

# 🧩 Phase 1 – SQL Business Case Study

The original SQL case study answers eight core business questions.

| # | Question |
|---|---|
| Q1 | Top 10 most expensive restaurants, with location and price tier |
| Q2 | Rating & vote data quality: zero ratings, zero votes, nulls |
| Q3 | Indian restaurants serving Indian cuisine without online delivery |
| Q4 | High-performing, budget-friendly restaurants (Rating ≥ 4.5, Votes > 500, Cost < ₹800) |
| Q5 | Online-delivery adoption by city |
| Q6 | Cities with delivery but no table booking |
| Q7 | Most popular cuisine by city (by votes) |
| Q8 | Cities whose average dining cost exceeds the overall average |

---

# 🔬 Phase 2 – Python EDA & Advanced Analysis

The second notebook extends the SQL case study from **Q9 onward**: dataset overview, data-quality checks, country and city distribution, rating and price analysis, delivery adoption, engagement by city and vote band, cuisine engagement, correlation analysis, segmentation, value-for-money analysis, city market profiling and a project-defined Market Opportunity Score.

> ⚠️ Several Phase 2 rating and city-level conclusions were revised in Phase 3. See [What Changed in Phase 3](#-what-changed-in-phase-3).

### Key Analytical Decision: Validate Context Before Interpreting

The dataset mixes **15 countries and 12 currency labels** (some mislabelled — e.g. "Dollar" covers four countries, the Philippines shows "Botswana Pula"). Raw `Average_Cost_for_two` values therefore cannot be compared across countries.

| Relationship | All countries | India only |
|---|---:|---:|
| Average Cost ↔ Price Range | **0.08** | **0.84** |
| Votes ↔ Average Cost | 0.07 | 0.28 |
| Votes ↔ Price Range | 0.31 | 0.31 |

The jump from **0.08 to 0.84** shows why analytical context matters: a technically correct calculation can still mislead if the variables are not comparable.

> **Correlation shows association, not causation.**

### Still-valid Phase 2 findings

- India = **90.6%** of records; New Delhi alone has **5,473** restaurants
- **0** duplicate Restaurant IDs; **9** missing cuisine values (none in India)
- Delivery adoption is highest in mid-priced segments: Price Range 2 **44.8%**, Range 3 **35.8%**, Range 1 **16.3%**, Range 4 **11.1%**
- Value-for-money restaurants (Rating ≥ 4.5, Votes > 500, Cost < ₹800) exist across price ranges 1–2
- Advanced SQL: most-voted cuisine per city using CTEs and `ROW_NUMBER()`

---

# 📊 Phase 3 – Data Cleaning (Python) + Power BI Dashboard

## Scope: India only

| Reason | Evidence |
|---|---|
| Concentration | India has **8,652 of 9,551** restaurants (90.6%) |
| Currencies | 12 currency labels with no conversion rate, some mislabelled |
| Delivery data | Online delivery is recorded only for India (28%) and UAE (47%, but only 60 restaurants) |
| Sample size | No other country has more than 434 restaurants; most have 20–80 |

## Data Cleaning (Python, VS Code)

| # | Issue | Rows affected | Treatment | Impact |
|---|---|---|---|---|
| 1 | Rating 1.0 used as placeholder (fewer than 4 votes) | 2,139 | Set to blank; flagged with `is_rated` | Avg rating 2.77 → **3.35** |
| 2 | Average cost for two = 0 | 9 | Set to blank | Minimal (₹623 → ₹624) |
| 3 | Small cities (≤ 20 restaurants) | 33 of 43 cities | City comparisons limited to cities with 100+ restaurants | Avoids small-sample bias |
| 4 | 12 currency labels, some mislabelled | 15 countries | Scope limited to India (₹) | Costs comparable |
| 5 | `Is_delivering_now` is a point-in-time snapshot | Whole column | Dropped | Avoids a misleading metric |
| 6 | `Switch_to_order_menu` has one value only | Whole column | Dropped | No information lost |

**Feature engineering:** `is_rated`, `rating_clean`, `cost_clean`, `online_delivery_flag`, `table_booking_flag`, `cuisines_clean`, `cuisine_count`, `cuisine_group` (1–5+), and an exploded **restaurant–cuisine bridge table** (17,854 rows).

**Outputs:** `zomato_india.csv` (8,652 × 16), `zomato_india_cuisines.csv`, `zomato_global.csv`.

## Dashboard (6 pages)

| Page | Question it answers |
|---|---|
| 1. Dataset Overview & Scope | Why India only? |
| 2. Data Quality & Cleaning | What was wrong with the raw data, and how much did fixing it matter? |
| 3. Market Overview | Where are India's restaurants, and how do the main cities compare? |
| 4. Ratings & Engagement | How are restaurants rated, and what drives votes? |
| 5. Price & Value | Does paying more get a better-rated restaurant? Where is the best value? |
| 6. Delivery & Services | Who offers delivery and table booking, and where is the opportunity? |

### Dashboard Preview

📄 [View the full 6-page dashboard (PDF)](Powerbi/Zomato%20Powerbi%20-%20pdf.pdf)

## Key Findings (cleaned data)

### Market
- **Delhi NCR holds 92%** of India's restaurants (7,947 of 8,652); New Delhi alone holds 63%.
- Only **4 of 43 cities** have 100+ restaurants (New Delhi, Gurgaon, Noida, Faridabad).
- **Gurgaon** leads on delivery (38.0%), rated share (79.6%) and price (₹714 for two). **Faridabad** trails on all (13.9% delivery, ₹448).
- At Gurgaon's delivery rate, New Delhi would have **~592 more** restaurants on delivery.

### Ratings & Engagement
- Ratings cluster between **2.8 and 3.8**; **42%** are rated "Average" and only **9%** "Very Good" or better.
- **25%** of restaurants are *not rated yet* (fewer than 4 votes).
- Excellent restaurants average **1,184 votes — ~25× more** than Average ones (48). Poor restaurants (88) also out-vote Average ones: customers vote most at the extremes.
- More cuisines, more engagement: average votes rise from **69** (1 cuisine) to **387** (5+), ratings from 3.30 to 3.63 — and the pattern holds within the same price range.

### Price & Value
- Half of all restaurants are **Budget** (avg ₹285 for two); **61%** cost ₹500 or less. Median meal for two: **₹450**.
- Ratings rise with price — **3.20 → 3.31 → 3.68 → 3.74** — but Luxury adds only +0.06 over Premium for twice the cost.
- Only **60%** of Budget restaurants are rated, vs **97%** of Premium and Luxury.
- Best-value localities (20+ restaurants, rating ≥ 3.5, ranked by rating per ₹1,000): **Jama Masjid** (3.56 at ₹319), Sector 37 Noida, Vijay Nagar.

### Delivery & Services
- **64%** of restaurants offer neither online delivery nor table booking.
- Delivery is a **mid-market** service (peaks at 44.8% in Mid-range); table booking is a **premium** service (56% Premium, 65% Luxury, ~0% Budget).
- Restaurants offering both services average **471 votes vs 90** for neither. Within Budget alone, delivery restaurants average **81 votes vs 28**.
- **6,229** restaurants don't deliver. Biggest locality gaps: **Shahdara** (87 restaurants, 0% delivery) and **Connaught Place** (70 not delivering despite a 3.78 rating).

## Power BI Techniques Used

- Star-style model: `zomato_india` (1) → `zomato_india_cuisines` (*), plus a separate `zomato_global` table for the scope page
- DAX measures: `COUNTROWS`, `AVERAGE`, `DIVIDE`, `CALCULATE`, `ALL`, `ALLEXCEPT`, `ALLSELECTED`, `DISTINCTCOUNT`, `MEDIAN`, `RANKX`, `SELECTEDVALUE`, `VAR/RETURN`
- Calculated columns: rating bands with custom sort order, service mix, city-size buckets
- `RANKX` + `ALLSELECTED` ranking with eligibility rules (replacing Top N, which applies before measure filters)
- Conditional formatting driven by a measure (highlight India in the country chart)
- `DATATABLE` for an in-model data-cleaning log
- Custom theme JSON, page backgrounds and page-navigation buttons

---

# 🧮 Analytical Framework

```text
PHASE 1 – SQL BUSINESS CASE STUDY
├── Q1–Q8  Pricing, data quality, delivery, budget performers,
│          table booking, cuisine popularity, city dining cost

PHASE 2 – PYTHON EDA & ADVANCED ANALYSIS
├── Q9–Q21 Overview, data quality, distributions, delivery,
│          engagement, cuisine engagement
├── Correlation (global vs India)
├── Segmentation, value-for-money, city profile
└── Market Opportunity Score  →  retired in Phase 3

PHASE 3 – DATA CLEANING + POWER BI
├── Placeholder-rating and sampling-cap discovery
├── Cleaned India dataset + cuisine bridge table
├── 6-page dashboard with DAX measures
└── Corrections log for Phase 2 findings
```

---

# 🛠️ Technology Stack

| Tool | Purpose |
|---|---|
| **SQL / SQLite** | Business-question analysis |
| **Python / Pandas** | EDA, data cleaning, feature engineering |
| **Matplotlib / Seaborn** | Distributions and correlation heatmaps |
| **Power BI / DAX** | Data model, measures, interactive dashboard |
| **Jupyter / VS Code / Google Colab** | Notebook development |
| **GitHub** | Version control and portfolio presentation |

---

# 🧠 Skills Demonstrated

**SQL:** aggregations, `GROUP BY` / `HAVING`, `CASE`, subqueries, CTEs, window functions (`ROW_NUMBER()`)

**Python:** `isna`, `duplicated`, `describe`, `value_counts`, `groupby` / `agg`, `pivot_table`, `crosstab`, `map`, `where`, `str.split` / `explode`, `clip`, feature engineering, confounder checks

**Power BI:** data modelling, DAX measures and calculated columns, ranking logic, conditional formatting, theming, navigation

**Business analytics:** data-quality validation, scope decisions, sample-bias detection, pricing and value analysis, delivery-gap sizing, insight writing, correcting earlier conclusions

---

# 📂 Repository Structure

```text
Zomato-Restaurant-Business-Analysis/
│
├── README.md
├── data/
│   ├── Zomato.xlsx                     (raw dataset)
│   ├── zomato_india.csv                (cleaned India data, 8,652 × 16)
│   ├── zomato_india_cuisines.csv       (restaurant–cuisine bridge, 17,854 rows)
│   └── zomato_global.csv               (all countries, for the scope page)
├── notebooks/
│   ├── Zomato_Market_Analysis_&_Business_Question_using_SQL.ipynb   (Phase 1)
│   ├── Zomato_Case_Study_Continuation_EDA_Advanced.ipynb            (Phase 2)
│   └── zomato_eda.ipynb                                             (Phase 3 – cleaning)
└── Powerbi/
    ├── Zomato.pbix                     (Power BI file)
    └── Zomato Powerbi - pdf.pdf        (6-page dashboard export)
```

---

# ⚠️ Analytical Limitations

1. The dataset is a single snapshot; no trends over time can be inferred.
2. Outside Delhi NCR, most cities are capped at ~20 listings, so city-level results there describe a sample, not the market.
3. Restaurants with fewer than 4 votes carry no real rating and are excluded from rating averages.
4. Votes are recorded engagement, not unique customers or orders.
5. Global cost comparisons are not valid without currency normalisation; the dashboard is India-only.
6. Correlation and group comparisons show association, not causation.
7. Segmentation and value thresholds are project-defined, not official Zomato metrics.
8. Recommendations should be validated with current operational data before use.

---

# 👤 Author

**Vijay Kumar**
Business Analytics | SQL | Python | Power BI
Portfolio: [vijaybsbs.github.io](https://vijaybsbs.github.io/)

---

## ⭐ Project Summary

This project shows an analyst's full loop on one dataset: **ask questions in SQL, explore in Python, then go back, find what the earlier analysis missed, and correct it**.

The two most important findings were not market insights but data insights — a placeholder rating that disguised 25% of restaurants as "low-rated", and a 20-listing cap that made small cities look like stronger markets than New Delhi. Fixing both changed the story, and the dashboard is built on the corrected data.

**Understand → Validate → Analyse → Question → Correct → Visualise → Recommend**
