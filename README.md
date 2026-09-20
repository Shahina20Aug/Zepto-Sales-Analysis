# 📊 Zepto Sales Analytics Dashboard

An end-to-end **Excel data analytics project** — from raw transactional data to a fully interactive, presentation-ready dashboard — built on a quick-commerce (instant delivery) sales dataset.

![Excel](https://img.shields.io/badge/Tool-Microsoft%20Excel-217346?style=flat&logo=microsoft-excel&logoColor=white)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen)
![Type](https://img.shields.io/badge/Type-Data%20Analytics%20Project-purple)

---

## 📌 Overview

This project analyses **1,498 orders** placed by **300 business customers** across **200 products**, worth a combined **₹5,63,332.74** in sales, for a quick-commerce platform (Zepto) operating out of **Bangalore, Delhi, and Mumbai** between January and March 2025.

The workflow takes the data from a raw, unprocessed state through validation, KPI calculation, 21 PivotTable-driven analyses, and finally into a single, dark-themed interactive dashboard — all inside one Excel workbook, with zero external tools or add-ins required.

> 📄 A full written project report is available in [`Zepto_Sales_Dashboard_Documentation.docx`](./Zepto_Sales_Dashboard_Documentation.docx).

---

## 📁 Repository Structure

```
zepto-sales-dashboard/
│
├── zepto_sales_raw.xlsx                     # Raw, unprocessed source data
├── zepto_sales_Analysis.xlsx                # Full analysis workbook (data + KPIs + charts + dashboard)
├── Zepto_Sales_Dashboard_Documentation.docx  # Detailed project documentation
└── README.md                                 # You are here
```

### Inside `zepto_sales_Analysis.xlsx`

| Sheet | Contents |
|---|---|
| `Sheet1` | Cleaned, validated order-level data (1,498 rows × 25 columns) |
| `KPIs` | Six headline summary metrics |
| `Charts` | 21 PivotTables + native Excel charts, one per business question |
| `Sheet2` / `Dashboard` | Final consolidated interactive dashboard |

---

## 🗂️ Dataset

Each row represents a single order line, combining order metadata, customer attributes, product detail, and a full pricing breakdown.

| Field group | Columns |
|---|---|
| **Order metadata** | `Order_ID`, `Order_Date`, `Days`, `Date`, `Day`, `Month`, `Year` |
| **Customer attributes** | `Customer_Name`, `Customer_Type`, `Customer_Segment`, `City` |
| **Product detail** | `SKU`, `Product_Name`, `Category`, `Qty` |
| **Pricing breakdown** | `Price`, `Discount`, `Subtotal`, `Tax`, `Delivery_Fee`, `Surge_Fee`, `Sales` |
| **Fulfilment** | `Payment_Method`, `Delivery_Status`, `Delivery_Time` |

---

## 🛠️ Tools & Techniques

- **Microsoft Excel PivotTables** — aggregation via SUM / COUNT / DISTINCT COUNT
- **Native Excel Charts** — Bar, Line, Area, and Doughnut charts bound directly to PivotTable output
- **Formula-based validation** — cross-checking derived fields for data integrity
- **Dashboard design** — single-sheet, dark-themed layout for stakeholder presentation

---

## 🔁 Project Workflow

### 1. Data Intake
Raw order-level data (`zepto_sales_raw.xlsx`) was imported into the workbook — 1,498 rows across 25 columns, covering orders from **1 Jan 2025 to 1 Mar 2025**.

### 2. Data Cleaning & Validation
| Check | Outcome |
|---|---|
| Duplicate `Order_ID` check | No duplicates found across 1,498 rows |
| Data type validation | Dates, numeric, and text fields all correctly typed |
| Missing value scan | `City` was the only field with gaps — 28 rows (≈1.9%) |
| Missing value treatment | Blank `City` values were **kept**, not dropped, and grouped under an explicit `N/A` category in city-based PivotTables — preserving ≈₹12,171 in otherwise-valid revenue |
| Derived field cross-check | `Sales = Subtotal + Tax + Delivery_Fee + Surge_Fee` and `Subtotal = (Qty × Price) − Discount` verified to reconcile exactly |
| Date decomposition | `Order_Date` pre-split into `Day` / `Month` / `Year` / weekday name for direct PivotTable grouping |

### 3. KPI Calculation
Six headline metrics were calculated on the `KPIs` sheet:

| KPI | Value |
|---|---|
| Total Sales | ₹5,63,332.74 |
| Total Orders | 1,498 |
| Total Customers | 300 |
| Total Products | 200 |
| Total Quantity Sold | 4,199 units |
| Average Sales per Order | ₹376.06 |

### 4. Exploratory Analysis (21 PivotTables + Charts)
Each analysis on the `Charts` sheet answers a specific business question, for example:

- Top / Bottom 10 orders, customers, and SKUs by sales
- Sales trend across months
- Daily sales, subtotal, and quantity volume
- Sales by city, payment method, customer type, and customer segment
- Customer-type performance by city and payment method (cross-tab)
- Delivery outcome by customer segment (cross-tab)

Every chart is bound live to its PivotTable, so the whole sheet recalculates automatically if the source data changes.

### 5. Dashboard Build
The five most decision-relevant visuals were consolidated onto a single dark-themed sheet (`Sheet2`), titled **"Zepto Sales Analysis"**:

- 🍩 Payment Methods Distribution
- 📈 Quantity of Sales Over Days
- 📊 Top 10 Orders
- 📊 Top 10 Products
- 🍩 Customers by City

---

## 💡 Key Insights

- **UPI dominates payments** — 491 of 1,498 orders (32.8%), contributing 33.4% of total revenue.
- **Bulk customers drive the business** — 83.3% of total revenue (₹4,69,386.34) comes from Bulk-type customers.
- **Bangalore leads by revenue** (₹2,01,206.68, 35.7%), narrowly ahead of Delhi and Mumbai.
- **Office is the top-performing customer segment** (₹1,03,708.09), ahead of Tea Stall, Café, Household, Cloud Kitchen, and Bakery.
- **83.7% delivery success rate** — 1,254 of 1,498 orders delivered; the rest split across Cancelled, Failed, and Returned.
- **January and February carry the data** (₹2,82,163.61 and ₹2,70,486.75) — March has only a single day of records and should be excluded from trend comparisons.

---

## 🚀 How to Use This Project

1. Clone or download this repository.
2. Open `zepto_sales_Analysis.xlsx` in Microsoft Excel.
3. Navigate to the `Dashboard` / `Sheet2` tab for the consolidated view.
4. Explore individual analyses on the `Charts` sheet, or the raw data on `Sheet1`.
5. To refresh with new data, replace the rows on `Sheet1` and refresh all PivotTables (`Data` → `Refresh All`).

---

## 🔭 Future Scope

- Add slicers / a date-range control for interactive filtering by month, city, or segment
- Extend the dataset beyond Q1 2025 for genuine month-over-month trend analysis
- Build a customer-retention / cohort view using the `Customer_Type` field
- Migrate the logic to Power BI or Python (pandas) for larger-scale, automated refreshes

---

## 👤 Author

**Viswa Desikan**
B.Tech, Artificial Intelligence & Data Science
Mahendra Engineering College (Autonomous), Namakkal

