# Veda-Technology-Task-26
# 📊 Executive KPI Dashboard (Power BI)

---

##  Objective

Design a concise business report that lets executives see the health of the business at a glance and slice it by year, region, category and segment, all on a single page.


##  Repository Structure

```
├── data/
│   ├── Superstore.csv          # Dataset (CSV)
│   └── Superstore.xlsx         # Dataset (Excel)
├── Task26_Executive_KPI_Dashboard.pbix   # Power BI file
├── Task26_Executive_KPI_Dashboard_Report.pdf   # 2-page report with KPI definitions
├── screenshots/
│   └── dashboard.png
└── README.md
```

##  Dataset

| Property | Details |
|---|---|
| Rows | 2,500 orders |
| Period | Jan 2023 – Dec 2025 |
| Columns | 16 |
| Geography | United States (4 regions, 12 states) |

**Columns:** Order ID, Order Date, Ship Date, Ship Mode, Customer Name, Segment, Country, State, Region, Category, Sub-Category, Quantity, Unit Price, Discount, Sales, Profit.

> **Note:** This is a synthetic Superstore-style dataset created for this exercise. The structure matches the popular Kaggle *Sample - Superstore* dataset, but the values are illustrative and will differ from the original.

##  KPIs and DAX Measures

Only five KPIs are shown, to keep the dashboard focused.

| KPI | Definition | DAX |
|---|---|---|
| **Total Sales** | Revenue after discounts | `SUM(Superstore_Task26[Sales])` |
| **Total Profit** | Revenue left after costs | `SUM(Superstore_Task26[Profit])` |
| **Profit Margin %** | Share of sales kept as profit | `DIVIDE([Total Profit], [Total Sales])` |
| **Total Orders** | Number of unique orders | `DISTINCTCOUNT(Superstore_Task26[Order ID])` |
| **Avg Discount** | Average discount per order line | `AVERAGE(Superstore_Task26[Discount])` |

##  Dashboard Components

| Component | Visual | Fields |
|---|---|---|
| KPI cards (5) | Card | The five measures above |
| Monthly Sales Trend | Line chart | Order Date (Month), Total Sales |
| Profit by Category | Clustered bar | Category, Total Profit |
| Sales by Segment | Donut chart | Segment, Total Sales |
| Sales by Region | Clustered bar | Region, Total Sales |
| Dynamic filters (4) | Slicers | Order Date (Year), Region, Category, Segment |

All visuals respond to every slicer, so any slice of the business can be explored without leaving the page.

## Key Insights

- **Overall:** $4.65M in sales and $306K in profit, with a 6.6% profit margin.
- **Category:** Technology drives most of the revenue ($3.46M). Furniture has a negative margin (about -3.5%), so it needs attention.
- **Region:** Central is the strongest region ($1.36M); South is the weakest ($1.03M).
- **Segment:** Consumer contributes the largest share of sales (47%).
- **Discounting:** Higher discounts pull margins down, so discount levels should be monitored, especially in low-margin categories.

##  Tools Used

- **Power BI Desktop**: data modelling, DAX and visualisation
- **DAX**: calculated measures
- **CSV / Excel**: data source

## Made By

**Akshat Srivastava**
Data Analytics Intern, Veda Technology

---
