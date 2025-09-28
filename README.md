# Financial Dashboard — Power BI

## 📌 Project Overview

This project is an **interactive financial dashboard** built in **Power BI** using the **Financial Sample dataset** provided with Power BI.
The dashboard is designed for **business stakeholders** to track key performance metrics, analyze sales and profit trends, and drill into details for decision-making.

---

## 🎯 Business Problem

Stakeholders often face challenges understanding financial performance across different products, segments, and regions. The dashboard provides:

* **At-a-glance KPIs** (Sales, Profit, Growth, Margin).
* **Time-series analysis** for trends and YoY comparison.

---

## 📂 Dataset

* **Source**: Financial Sample.xlsx (bundled with Power BI Desktop).
* **Key fields**: Date, Country, Segment, Product, Sales, Profit, COGS, Units Sold.
* **Data modeling**: One fact table (Financials) + one Date table (created with DAX).

---

## ⚙️ Data Modeling & DAX

* Built a **Date table** using `CALENDARAUTO()` and marked it as a Date table.
* Defined relationships between the Date table and Financials.
* Created core measures in DAX:

  * `Total Sales = SUM(Financials[Sales])`
  * `Total Profit = SUM(Financials[Profit])`
  * `Profit Margin % = DIVIDE([Total Profit], [Total Sales], 0)`
  * `Sales LY = CALCULATE([Total Sales], DATEADD('Date'[Date], -1, YEAR))`
  * `YoY Growth % = DIVIDE([Total Sales]-[Sales LY],[Sales LY])`
  * `Sales YTD = TOTALYTD([Total Sales], 'Date'[Date])`

---

## 📊 Dashboard Pages

### 1. **Overview (Executive)**

* KPI cards: Total Sales, Total Profit, Profit Margin %, YoY Growth %.
* Sales trend vs. last year (line chart).
* Sales by Country (bar chart).
* Profit by Segment (pie chart).
* Sales by Product (donut chart).

### 2. **Sales & Profit Analysis**

* Slicers for Date, Country, Segment, Product.
* Line chart: Sales vs Profit trend by Product.
* Waterfall chart: Profit breakdown by Segment.
* Matrix table: Country → Segment → Sales, Profit, Margin.

---

## 🖱️ Interactivity 

* **Slicers**: Country, Product, Segment, and Date (synced across pages).
* **Tooltips** for quick contextual insights.

---

## 📈 Insights & Value

* Track **Sales and Profit growth** over time.
* Compare performance **YoY** to identify improvement or decline.
* Identify **profitable/unprofitable segments** for resource allocation.
* Spot **top-performing countries/products** to guide strategy.

