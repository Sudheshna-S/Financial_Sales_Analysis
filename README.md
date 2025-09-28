# Financial Dashboard — Power BI

## 📌 Project Overview

This project is an **interactive financial dashboard** built in **Power BI** using the **Financial Sample dataset** provided with Power BI.
The dashboard is designed for **business stakeholders** to track key performance metrics, analyze sales and profit trends, and drill into details for decision-making.

---

## 🎯 Business Problem

Stakeholders often face challenges understanding financial performance across different products, segments, and regions. The dashboard provides:

* **At-a-glance KPIs** (Sales, Profit, Growth, Margin).
* **Time-series analysis** for trends and YoY comparison.
* **Interactive drilldowns** to uncover product and country-level insights.
* **Navigation menu** for a structured, user-friendly reporting experience.

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
* Profit by Segment (column chart).
* Sales by Product (donut chart).

### 2. **Sales & Profit Analysis**

* Slicers for Date, Country, Segment, Product.
* Line chart: Sales vs Profit trend.
* Waterfall chart: Profit breakdown by Product/Segment.
* Matrix table: Country → Segment → Sales, Profit, Margin.

### 3. **Detail Drillthrough**

* Drillthrough enabled for Product and Country.
* Detailed transaction-level table with Sales, Profit, COGS, Units Sold.

---

## 🖱️ Interactivity & Navigation

* **Slicers**: Country, Product, Segment, and Date (synced across pages).
* **Drillthrough pages** for detailed analysis.
* **Custom navigation menu** built with Bookmarks & Buttons for a clean, app-like experience.
* **Tooltips** for quick contextual insights.

---

## 🎨 Design Choices

* Consistent corporate color scheme (blue for positive, red for negative).
* Large KPI cards placed at the top for instant visibility.
* Bookmark navigation placed on the left for easy access.
* Dynamic titles added for better context (e.g., “Total Sales — Last 12 Months vs LY”).

---

## 🚀 How to Use

1. Open the `.pbix` file in Power BI Desktop.
2. Use the **navigation menu** (left sidebar) to move between Overview, Analysis, and Detail pages.
3. Apply slicers to filter by Date, Country, Segment, or Product.
4. Hover over charts for tooltips with extra insights.
5. Right-click a Product/Country to drillthrough into the Detail page.

---

## 📈 Insights & Value

* Track **Sales and Profit growth** over time.
* Compare performance **YoY** to identify improvement or decline.
* Identify **profitable/unprofitable segments** for resource allocation.
* Spot **top-performing countries/products** to guide strategy.

---

## 🔮 Next Steps / Extensions

* Automate data refresh by connecting to a live database.
* Add **forecasting visuals** for sales prediction.
* Implement **Row-Level Security (RLS)** for stakeholder-specific access.
* Connect to external datasets (market trends, currency exchange) for deeper context.

---

**Author:** [Your Name]
**Tool:** Microsoft Power BI Desktop
**Dataset:** Financial Sample.xlsx (Power BI sample data)
