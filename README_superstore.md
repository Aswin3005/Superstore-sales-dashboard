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

![Overview](screenshots/overview.png)

---

### 2. 📦 Product Analysis
Sub-category level deep dive — revenue, profit margin, return rate, and Top/Bottom N filtering to surface best and worst performers. Identified that **Binders**, the top-selling Office Supplies sub-category, saw a **profit margin collapse from 20.6% → 10.5% YoY** — the primary driver of the overall 0.7-point margin decline.

![Product](screenshots/product.png)

---

### 3. 👤 Customer Analysis
Customer segmentation by sales volume and order frequency. Dynamic Top/Bottom N visual to rank customers. Identifies high-value and at-risk customers for targeted retention or upsell strategies.

![Customer](screenshots/customer.png)

---

### 4. 🗺️ Regional Analysis
State-level profitability map with margin benchmarks. Key finding: **Central region's weak 7.92% margin** was traced to **Texas and Illinois**, both posting margins below -15%. Contrasts with **New York (23.8%)** and **California (16.7%)** on similar sales volumes. **10 states are currently unprofitable.**

![Regional](screenshots/regional.png)

---

### 5. 🔄 Returns Analysis
Return rate by category, sub-category, and region. Helps operations and supply chain teams identify which products and regions have disproportionately high return rates affecting net margin.

![Returns](screenshots/returns.png)

---

### 6. 📈 Forecast Page
12-month sales and profit forecast using Power BI's built-in seasonal trend analysis with a **95% confidence interval**. Includes a **trend-based target gauge** that benchmarks projected performance against the historical average growth rate.

![Forecast](screenshots/forecast.png)

---

### 7. 🔍 Detailed Info (Drillthrough)
Transaction-level drillthrough page accessible from any summary table. Allows users to right-click any product or customer and navigate directly to their individual order history — replicating the analyst workflow of "zoom in on an outlier."

![Drillthrough](screenshots/drillthrough.png)

---

## 🧠 DAX Measures (30+)

Key measures built for this report:

```dax
-- Year-over-Year Sales Growth
YoY Sales Growth % =
VAR CurrentYearSales = [Total Sales]
VAR PriorYearSales = CALCULATE([Total Sales], SAMEPERIODLASTYEAR('Date'[Date]))
RETURN DIVIDE(CurrentYearSales - PriorYearSales, PriorYearSales)

-- Profit Margin
Profit Margin % =
DIVIDE([Total Profit], [Total Sales], 0)

-- Dynamic Top N Customers
Top N Customers Sales =
CALCULATE(
    [Total Sales],
    TOPN([Top N Value], ALL('Customer'), [Total Sales], DESC)
)

-- Running Total Sales (for trend line)
Running Total Sales =
CALCULATE(
    [Total Sales],
    FILTER(
        ALL('Date'[Date]),
        'Date'[Date] <= MAX('Date'[Date])
    )
)
```

> Full measure list available inside the .pbix file under the **Measures** table.

---

## 🗂️ Data Model

Normalised star schema with fact and dimension tables:

```
Fact_Orders ──> Dim_Customer
           ──> Dim_Product
           ──> Dim_Geography
           ──> Dim_Date
           ──> Dim_Shipping
```

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

---

## 📁 Files

| File | Description |
|------|-------------|
| `Superstore_Dashboard.pbix` | Full Power BI report file |
| `screenshots/` | Page-by-page screenshots of the report |

---

## 👤 Author

**Aswin**  
Aspiring Data Analyst  
[LinkedIn](https://linkedin.com/in/your-profile) | [GitHub](https://github.com/Aswin3005)
