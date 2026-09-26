# 🛒 Superstore Sales Analytics Dashboard — Power BI

**Tool:** Power BI Desktop  
**Skills:** DAX, Power Query, Data Modelling, BI Storytelling, Forecasting  
**Dataset:** Sample Superstore — 5,009 orders · 793 customers · $22.97L in sales  

---

## 📌 Project Overview

An end-to-end business intelligence solution built on the Sample Superstore dataset, designed to simulate the kind of executive-facing dashboard a BI Analyst or Data Analyst would deliver in a retail or e-commerce environment.

The report goes beyond simple charts — it includes a normalised data model, 30+ DAX measures, drillthrough navigation, dynamic filtering, and a 12-month sales forecast with confidence intervals.

---

## 📊 Report Pages (7 Pages)

### 1. 🏠 Overview
Top-level KPIs — total sales, profit, orders, and customers. YoY trend lines and a high-level summary of performance across all categories and regions. Entry point for executives who need a 30-second snapshot.

<img width="1455" height="818" alt="Image" src="https://github.com/user-attachments/assets/704063fb-9537-419a-ad89-6516045b3236" />

---

### 2. 📦 Product Analysis
Sub-category level deep dive — revenue, profit margin, return rate, and Top/Bottom N filtering to surface best and worst performers. Identified that **Binders**, the top-selling Office Supplies sub-category, saw a **profit margin collapse from 20.6% → 10.5% YoY** — the primary driver of the overall 0.7-point margin decline.

<img width="1418" height="815" alt="Image" src="https://github.com/user-attachments/assets/327dfd54-2759-4e7c-a91d-bf803014d363" />

---

### 3. 👤 Customer Analysis
Customer segmentation by sales volume and order frequency. Dynamic Top/Bottom N visual to rank customers. Identifies high-value and at-risk customers for targeted retention or upsell strategies.

<img width="1424" height="810" alt="Image" src="https://github.com/user-attachments/assets/235dc2c0-a3ea-40ce-ad46-9072e17dd615" />

---

### 4. 🗺️ Regional Analysis
State-level profitability map with margin benchmarks. Key finding: **Central region's weak 7.92% margin** was traced to **Texas and Illinois**, both posting margins below -15%. Contrasts with **New York (23.8%)** and **California (16.7%)** on similar sales volumes. **10 states are currently unprofitable.**

<img width="1441" height="818" alt="Image" src="https://github.com/user-attachments/assets/697ba951-ef96-4c12-9c9f-54e94069f14d" />

---

### 5. 🔄 Returns Analysis
Return rate by category, sub-category, and region. Helps operations and supply chain teams identify which products and regions have disproportionately high return rates affecting net margin.

<img width="1428" height="815" alt="Image" src="https://github.com/user-attachments/assets/4663c3b2-965c-4e99-9427-5631085842d2" />

---

### 6. 📈 Forecast Page
12-month sales and profit forecast using Power BI's built-in seasonal trend analysis with a **95% confidence interval**. Includes a **trend-based target gauge** that benchmarks projected performance against the historical average growth rate.

<img width="1431" height="810" alt="Image" src="https://github.com/user-attachments/assets/e6d341b0-bedc-4822-a299-203f1f10cfaf" />

---

### 7. 🔍 Detailed Info (Drillthrough)
Transaction-level drillthrough page accessible from any summary table. Allows users to right-click any product or customer and navigate directly to their individual order history — replicating the analyst workflow of "zoom in on an outlier."

<img width="1425" height="813" alt="Image" src="https://github.com/user-attachments/assets/a6aa9e40-47b9-48a8-9cee-d2beb8142e9f" />

---

## 🗂️ Data Model

Normalised star schema with fact and dimension tables:

<img width="1796" height="868" alt="Image" src="https://github.com/user-attachments/assets/907d9d90-9b7a-42d4-a789-ab897f3b611d" />


Power Query was used to split the raw flat file into dimension tables, remove duplicates, standardise data types, and create the date table with fiscal calendar columns.

---

## ✨ Features

| Feature | Description |
|---------|-------------|
| **Dynamic Top/Bottom N** | Slicer-controlled ranking on product and customer visuals |
| **Drillthrough Navigation** | Right-click from any summary → transaction detail page |
| **12-Month Forecast** | Seasonal trend with 95% confidence interval bands |
| **Target Gauge** | Benchmarks projected growth vs. historical average |
| **Collapsible Slicer Panel** | Date, Category, Sub-Category, Region, State filters |
| **Conditional Formatting** | Color-coded margins, profit flags, and trend indicators |
| **Insight Callouts** | Each page includes a written insight box explaining the key finding |
| **Consistent Design System** | Shared color palette, font, and layout applied across all 7 pages |

<img width="1441" height="808" alt="Image" src="https://github.com/user-attachments/assets/edc3d232-25c6-40a6-a9aa-a68f74b36ef4" />

---

## 🔑 Key Findings

| Finding | Detail |
|---------|--------|
| YoY margin decline | Profit margin dropped 0.7 points overall |
| Root cause | Binders sub-category: margin fell from 20.6% → 10.5% |
| Regional risk | Central region margin 7.92% — dragged by TX (-15%+) and IL (-15%+) |
| Unprofitable states | 10 states currently loss-making |
| Best large market | New York at 23.8% margin vs California at 16.7% on similar volume |
| Forecast | 12-month projection suggests continued seasonality with Q4 peak |

---

## 💡 Business Recommendations

1. **Review Binders pricing or supplier costs** — a 10-point margin collapse in the top-selling sub-category is a critical issue requiring urgent attention
2. **Exit or restructure Texas and Illinois operations** — both states are significantly loss-making on meaningful sales volume
3. **Replicate New York's model** — at 23.8% margin it outperforms California on the same scale; investigate what's different (pricing, fulfilment costs, customer mix)
4. **Prioritise Q4 inventory planning** — the forecast shows a consistent seasonal peak; stock and staff accordingly
5. **Investigate high-return sub-categories** — returns directly erode net margin; target the top 3 return-rate products for quality or description improvements

---

## 🛠️ Tools & Skills

| Tool / Skill | Usage |
|---|---|
| Power BI Desktop | Report development, visuals, publishing |
| DAX | 30+ measures including YoY, running totals, dynamic Top N, margin |
| Power Query (M) | Data cleaning, table normalisation, date table creation |
| Data Modelling | Star schema, relationships, calculated columns |
| BI Storytelling | Insight callouts, drillthrough, executive summary page |
