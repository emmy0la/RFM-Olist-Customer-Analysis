# RFM Customer Analysis | Brazilian Ecommerce

SQL → Excel → Dashboard

Customer segmentation and retention analysis using the Olist Brazilian Ecommerce dataset.

---

# Project Overview

This project analyzes customer purchasing behavior using RFM Analysis (Recency, Frequency, Monetary).

The goal was to transform raw ecommerce transactional data into business insights that support:
- customer retention
- revenue optimization
- churn detection
- customer segmentation
- marketing decision-making

The analysis was performed using SQL for data transformation and Excel for dashboard visualization.

---

# Business Problem

The ecommerce business needed answers to key customer behavior questions:

- Who are the most valuable customers?
- Which customers are becoming inactive?
- Which customer groups generate the most revenue?
- How frequently do customers purchase?
- Where should retention and marketing efforts focus?

Without customer segmentation, the company risks:
- losing repeat customers
- inefficient marketing spending
- poor retention performance
- weak personalization strategies

---

# Project Objectives

- Build an analytical customer transaction dataset using SQL joins
- Create RFM metrics:
  - Recency
  - Frequency
  - Monetary
- Score customers using SQL logic
- Segment customers into business-focused groups
- Build an interactive dashboard in Excel
- Generate actionable business insights

---

# Dataset

## Source
Brazilian Ecommerce Public Dataset by Olist

## Tables Used
- olist_orders_dataset
- olist_customers_dataset
- olist_order_payments_dataset

## Final Analytical Tables
- customer_transactions
- customer_rfm_base
- customer_rfm_scores
- customer_segments

---

# Tools & Technologies

- SQL (SQLite)
- SQLite Online
- Excel
- Pivot Tables
- Pivot Charts
- Slicers
- GitHub

---

# Database Relationship Model

The project uses relational joins across:
- Customers
- Orders
- Payments

Relationship flow:

Customers → Orders → Payments

## ER Diagram

![images/er_diagram.png](https://github.com/emmy0la/RFM-Olist-Customer-Analysis/blob/acbe36365dd7a9eb69c058e85c9c9dfef5cf03aa/Images/ER%20Diagram/ER_Diagram%201.png)
![Image/er_diagram.png](https://github.com/emmy0la/RFM-Olist-Customer-Analysis/blob/acbe36365dd7a9eb69c058e85c9c9dfef5cf03aa/Images/ER%20Diagram/ER_Diagram%202.png)

---

# SQL Analysis Workflow

## Phase 1: Data Exploration

Performed:
- row count validation
- NULL checks
- relationship checks
- date range inspection
- unique customer validation

![image/SQL execution screenshots.png](https://github.com/emmy0la/RFM-Olist-Customer-Analysis/blob/32653b2a11808010e7f17f2b42c88576ba800fe0/Images/SQL%20execution%20screenshots/NULL%20check.png)
![image/SQL execution screenshots.png](https://github.com/emmy0la/RFM-Olist-Customer-Analysis/blob/32653b2a11808010e7f17f2b42c88576ba800fe0/Images/SQL%20execution%20screenshots/Relationship%20validation.png)
![image/SQL execution screenshots.png](https://github.com/emmy0la/RFM-Olist-Customer-Analysis/blob/32653b2a11808010e7f17f2b42c88576ba800fe0/Images/SQL%20execution%20screenshots/JOIN%20preview.png)

## Phase 2: Transaction Dataset Creation

Built a clean transactional table using SQL JOIN operations.

Included:
- customer_id
- order_id
- purchase date
- payment value

![image/SQL execution screenshots.png](https://github.com/emmy0la/RFM-Olist-Customer-Analysis/blob/68c5c49c060e3b3a279ebb3ddecd14dbec0b4763/Images/SQL%20execution%20screenshots/Main%20JOIN%20query.png)
![image/SQL execution screenshots.png](https://github.com/emmy0la/RFM-Olist-Customer-Analysis/blob/68c5c49c060e3b3a279ebb3ddecd14dbec0b4763/Images/SQL%20execution%20screenshots/customer_transactions%20output%20preview.png)
![image/SQL execution screenshots.png](https://github.com/emmy0la/RFM-Olist-Customer-Analysis/blob/68c5c49c060e3b3a279ebb3ddecd14dbec0b4763/Images/SQL%20execution%20screenshots/duplicate%20validation%20OR%20repeat%20customer%20validation.png)

The RFM analysis was conducted using only delivered orders, ensuring every transaction represented a completed purchase and realized revenue. 

Raw relational tables were transformed into a clean, analysis-ready customer transaction dataset, providing the foundation for all Recency, Frequency, and Monetary calculations that followed.

## Phase 3: RFM Feature Engineering

Generated:
- recency_days
- total_orders
- total_spent

![image/SQL execution screenshots.png](https://github.com/emmy0la/RFM-Olist-Customer-Analysis/blob/68c5c49c060e3b3a279ebb3ddecd14dbec0b4763/Images/SQL%20execution%20screenshots/Main%20RFM%20engineering%20query.png)
![image/SQL execution screenshots.png](https://github.com/emmy0la/RFM-Olist-Customer-Analysis/blob/68c5c49c060e3b3a279ebb3ddecd14dbec0b4763/Images/SQL%20execution%20screenshots/customer_rfm_base%20output%20preview.png)
![image/SQL execution screenshots.png](https://github.com/emmy0la/RFM-Olist-Customer-Analysis/blob/68c5c49c060e3b3a279ebb3ddecd14dbec0b4763/Images/SQL%20execution%20screenshots/frequency%20distribution%20query.png)

The ransactional data was converted into customer-level business metrics - answering: How recent? How often? How much?

## Phase 4: Customer Scoring

Assigned:
- R Score
- F Score
- M Score

![image/SQL execution screenshots.png](https://github.com/emmy0la/RFM-Olist-Customer-Analysis/blob/68c5c49c060e3b3a279ebb3ddecd14dbec0b4763/Images/SQL%20execution%20screenshots/Main%20scoring%20query.png)
![image/SQL execution screenshots.png](https://github.com/emmy0la/RFM-Olist-Customer-Analysis/blob/68c5c49c060e3b3a279ebb3ddecd14dbec0b4763/Images/SQL%20execution%20screenshots/RFM%20scores%20output%20preview.png)

The raw customer behavior was transformed into measurable customer quality scores - each customer ranked 1-5 on Recency, Frequency, and Monetary - then segmented from Champions to Lost.

## Phase 5: Customer Segmentation
Segmented customers into behavioral groups using RFM scoring logic.

Segments created:
- Champions
- Loyal Customers
- Potential Loyalists
- New Customers
- At Risk
- Lost Customers
- Need Attention

![image/SQL execution screenshots.png](https://github.com/emmy0la/RFM-Olist-Customer-Analysis/blob/68c5c49c060e3b3a279ebb3ddecd14dbec0b4763/Images/SQL%20execution%20screenshots/Screenshot%202026-05-15%20122417.png)
![image/SQL execution screenshots.png](https://github.com/emmy0la/RFM-Olist-Customer-Analysis/blob/68c5c49c060e3b3a279ebb3ddecd14dbec0b4763/Images/SQL%20execution%20screenshots/segment%20distribution%20screenshot.png)
![image/SQL execution screenshots.png](https://github.com/emmy0la/RFM-Olist-Customer-Analysis/blob/68c5c49c060e3b3a279ebb3ddecd14dbec0b4763/Images/SQL%20execution%20screenshots/dashboard%20screenshot%20showing%20segment%20chart.png)

SQL logic was implemented using CASE statements based on Recency, Frequency, and Monetary scores - converting 1-5 rankings into customer segments: Champions, Loyal, At Risk, Lost, and Regular.

---

# Key Metrics

| Metric | Value |
|---|---|
| Total Customers | 93,357 |
| Total Orders | 96,477 |
| Total Revenue | $15.42M |
| Average Customer Spend | $165 |
| Average Recency | 237 Days |

---

# Dashboard Preview

![image/Dashboard screenshots.png](https://github.com/emmy0la/RFM-Olist-Customer-Analysis/blob/68c5c49c060e3b3a279ebb3ddecd14dbec0b4763/Images/Dashboard%20screenshots/Dashboard%20Screenshot.png)

---

# Key Business Insights

## 1. Customer Retention Problem

97% of customers purchased only once.

This indicates:
- weak customer retention
- low repeat purchase behavior
- dependency on new customer acquisition

## 2. Revenue Concentration

Medium-spending customers contribute the largest share of total revenue.

This means:
- retention strategies should focus heavily on mid-value customers
- small improvements in repeat purchases could significantly impact revenue

## 3. High Customer Recency

Average recency is 237 days.

This suggests:
- many customers have become inactive
- the business faces customer churn risk

## 4. Segment Distribution

Lost Customers and At Risk customers represent a large portion of the customer base.

This reveals:
- retention campaigns are urgently needed
- reactivation opportunities exist

## 5. Champions Segment

A smaller group of customers drives strong revenue contribution.

These customers should receive:
- loyalty incentives
- premium targeting
- personalized engagement

---

# Recommendations

| Recommendation | Business Goal |
|---|---|
| Launch win-back campaigns | Recover inactive customers |
| Create second-purchase incentives | Improve repeat purchase rate |
| Introduce loyalty programs | Retain high-value customers |
| Target At Risk customers early | Reduce churn |
| Personalize marketing campaigns | Increase engagement |

---

# Files Included

## SQL Scripts
- rfm_analysis_queries.sql
- segmentation_queries.sql

## Exported Datasets
- customer_rfm_base.csv
- customer_rfm_scores.csv
- customer_segments.csv

## Dashboard
- RFM_Customer_Analysis_Dashboard.xlsx

## Images
- Dashboard screenshots
- SQL execution screenshots
- ER Diagram

---

# SQL Skills Demonstrated

- SELECT
- JOIN
- GROUP BY
- HAVING
- CASE WHEN
- Aggregate Functions
- NULL Handling
- Filtering
- RFM Analysis
- Data Transformation
- Customer Segmentation Logic

---

# What I Learned

This project strengthened my understanding of:
- relational database analysis
- SQL joins and transformations
- customer behavior analytics
- RFM segmentation
- business storytelling with data
- dashboard reporting in Excel

I learned how to move from raw transactional data to actionable business decisions using SQL and BI reporting techniques.

---

# Author

Emmanuel Olawumi

Data Analyst | SQL | Excel | Business Intelligence | Digital Strategy
https://www.linkedin.com/in/emmanuelolawumi/
