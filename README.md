# 🛍️ Customer Shopping Behavior Analysis

> An end-to-end data analytics project uncovering consumer spending patterns, customer segments, and product preferences to drive smarter retail business decisions.

---

## 📌 Table of Contents

- [Project Overview](#project-overview)
- [Business Problem](#business-problem)
- [Dataset](#dataset)
- [Tech Stack](#tech-stack)
- [Project Pipeline](#project-pipeline)
  - [1. Data Loading & EDA (Python)](#1-data-loading--eda-python)
  - [2. Data Cleaning & Feature Engineering](#2-data-cleaning--feature-engineering)
  - [3. SQL Analysis (PostgreSQL)](#3-sql-analysis-postgresql)
  - [4. Power BI Dashboard](#4-power-bi-dashboard)
  - [5. Stakeholder Presentation](#5-stakeholder-presentation)
- [Key Findings](#key-findings)
- [Business Recommendations](#business-recommendations)
---

## Project Overview

This project delivers a full-cycle data analytics solution for a retail company looking to better understand its customers. The analysis spans raw data ingestion, exploratory analysis, SQL-based business queries, interactive dashboarding, and a stakeholder-ready presentation — covering the complete workflow from raw data to actionable insight.

---

## Business Problem

> *"How can the company leverage consumer shopping data to identify trends, improve customer engagement, and optimize marketing and product strategies?"*

A retail company noticed shifting purchasing patterns across demographics, product categories, and sales channels. Management needed clarity on which factors — discounts, reviews, seasonality, payment preferences — truly drive consumer decisions and repeat purchases.

---

## Dataset

| Property | Details |
|---|---|
| **Source** | [Kaggle](https://www.kaggle.com) |
| **Records** | 3,900 transactions |
| **Features** | 18 columns |
| **Domain** | Retail / Consumer Behavior |

**Feature Groups:**

- **Demographics** — Age, Gender, Location, Subscription Status
- **Purchase Details** — Item Purchased, Category, Purchase Amount (USD), Season, Size, Color
- **Behavioral** — Discount Applied, Promo Code Used, Previous Purchases, Frequency of Purchases, Review Rating, Shipping Type, Payment Method

---

## Tech Stack

| Tool | Purpose |
|---|---|
| **Python** (pandas, matplotlib, seaborn) | Data loading, EDA, cleaning, feature engineering |
| **PostgreSQL** | Structured business query analysis |
| **SQLAlchemy / psycopg2** | Python–PostgreSQL integration |
| **Power BI** | Interactive dashboard & KPI visualization |
| **Gamma** | Stakeholder presentation |
| **Jupyter Notebook** | Development environment |

---

## Project Pipeline

### 1. Data Loading & EDA (Python)

- Loaded the dataset using `pandas`
- Inspected structure with `df.info()` and summary statistics with `df.describe()`
- Identified **37 missing values** in the `Review Rating` column
- Visualized distributions across age, category, purchase amount, and season

### 2. Data Cleaning & Feature Engineering

| Step | Action |
|---|---|
| **Missing Values** | Imputed `review_rating` nulls using median rating per product category |
| **Column Standardization** | Renamed all columns to `snake_case` |
| **Redundancy Check** | Confirmed `discount_applied` and `promo_code_used` were redundant; dropped `promo_code_used` |
| **Feature: `age_group`** | Binned customer ages into Young Adult, Adult, Middle-aged, Senior |
| **Feature: `purchase_frequency_days`** | Derived from frequency of purchases column |
| **DB Integration** | Loaded cleaned DataFrame into PostgreSQL via Python for SQL analysis |

### 3. SQL Analysis (PostgreSQL)

Ten business questions were answered using structured SQL queries:

| # | Query | Insight |
|---|---|---|
| 1 | **Revenue by Gender** | Males generated $157,890 vs. Females $75,191 |
| 2 | **High-Spending Discount Users** | 839 customers used discounts yet spent above average |
| 3 | **Top 5 Products by Rating** | Gloves (3.86), Sandals (3.84), Boots (3.82), Hat (3.80), Skirt (3.78) |
| 4 | **Shipping Type Comparison** | Express avg. $60.48 vs. Standard avg. $58.46 |
| 5 | **Subscribers vs. Non-Subscribers** | Avg. spend nearly equal (~$59); non-subscribers drive 73% of total revenue |
| 6 | **Discount-Dependent Products** | Hat (50%), Sneakers (49.66%), Coat (49.07%) most discount-reliant |
| 7 | **Customer Segmentation** | Loyal: 3,116 · Returning: 701 · New: 83 |
| 8 | **Top 3 Products per Category** | Jewelry, Blouse, Sandals, Jacket lead their categories |
| 9 | **Repeat Buyers & Subscriptions** | 2,518 repeat buyers are non-subscribers — a major conversion opportunity |
| 10 | **Revenue by Age Group** | Young Adults lead at $62,143; revenue is fairly balanced across all groups |

### 4. Power BI Dashboard

An interactive **Customer Behavior Dashboard** was built featuring:

- **KPI Cards** — Total Customers (3.9K), Average Purchase Amount ($59.76), Average Review Rating (3.75)
- **Donut Chart** — Subscription Status split (Yes 27% / No 73%)
- **Bar Charts** — Revenue by Category, Sales by Category
- **Horizontal Bar Charts** — Revenue and Sales by Age Group
- **Slicers** — Filter by Subscription Status, Gender, Category, Shipping Type

### 5. Stakeholder Presentation

A business-ready presentation summarizing the full analysis, key findings, and strategic recommendations was built using Gamma.

🔗 [View Presentation](https://gamma.app/docs/Customer-Shopping-Behavior-Analysis-tl3fghvobangpy4)

---

## Key Findings

- 📊 **Male customers account for ~68% of total revenue** ($157,890 vs. $75,191)
- 🔁 **80% of the customer base is classified as Loyal**, indicating strong retention
- 💳 **73% of customers are non-subscribers** yet generate the majority of revenue — a major upsell opportunity
- 🏷️ **839 high-value customers still use discounts** — discounting doesn't necessarily reduce spend quality
- 👟 **Hats and Sneakers are the most discount-dependent products** (~50% of purchases use a discount)
- 🧑 **Young Adults are the highest revenue-contributing age group** at $62,143

---

## Business Recommendations

1. **Boost Subscriptions** — Promote exclusive subscriber benefits to convert the 73% non-subscriber base; target the 2,518 repeat buyers who haven't subscribed yet
2. **Loyalty Programs** — Reward returning customers to accelerate movement into the Loyal segment
3. **Discount Policy Review** — Re-evaluate heavy discounting on Hat, Sneakers, and Coat; test margin-neutral incentives
4. **Product Campaigns** — Feature top-rated products (Gloves, Sandals, Boots) in marketing materials to leverage social proof
5. **Targeted Marketing** — Prioritize Young Adult and Middle-aged segments with express-shipping-friendly offers

---

## Author

**Mohammed Adnan**

📎 [LinkedIn](https://linkedin.com/in/a-dnan)

---

*Feel free to ⭐ this repository if you found it useful!*
