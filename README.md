# 🛒 D-Mart Sales Dashboard (Power BI)

## 🚀 Project Overview
This project is an interactive **Power BI dashboard** built to analyze sales, profit, customer behavior, and return trends for a retail business (D-Mart).

It provides both **high-level summaries** and **deep-dive analytics** to help stakeholders understand business performance and take data-driven decisions.

---

## 🎯 Business Objectives
- Track sales, profit, and order volume
- Identify top-performing regions and categories
- Analyze customer contribution and segmentation
- Monitor return rates and product performance
- Evaluate quarterly and yearly growth trends

---

## 📊 Dashboard Structure

### 🟢 Main Dashboard (Overview Page)

#### 🔑 Key KPIs:
- 💰 **Total Sales:** 848K
- 💸 **Total Profit:** ₹162.17K
- 📦 **Total Orders:** 1000

#### 📈 Visuals:
- Sales by Quarter (Q1–Q4 comparison)
- Sales vs Profit by Region
- Orders Distribution by Category
- Quantity vs Returns Analysis
- Segment-wise Sales (SMB, Corporate, Retail)

#### 🎛 Filters:
- Quarter Selector
- Region Filter

---

### 🔵 Detail Dashboard (Deep Analysis)

#### 🔑 Key KPIs:
- 👥 Total Customers: 100
- 🔄 Return Orders: 100
- 🧠 Top Customer: Anthony Mccarthy
- 📉 Return Rate: 10%

#### 📊 Visuals:
- Customer-wise Sales & Profit Trends
- Quantity vs Customer Count by Region
- Return Quantity by Category
- Segment-wise Performance Comparison

#### 🎛 Filters:
- Category Selection (Books, Electronics, Toys, etc.)
- Region Filter (Central, North, West, etc.)

---

## 📌 Key Insights

- **Electronics category** dominates order volume (~33%)
- **West & Central regions** generate the highest sales
- **SMB segment** has the highest average sales
- **Clothing category** has the lowest performance but also lowest returns
- **Returns are significant in Electronics and Toys** → potential quality issues
- Sales and profit are **not aligned across regions**, indicating cost inefficiencies

---

## 🛠️ Tools & Technologies
- **Power BI Desktop**
- Power Query (ETL)
- DAX (Data Analysis Expressions)
- Data Modeling (Star Schema)

---

## ⚙️ Data Modeling
- Fact Table: Sales Data
- Dimension Tables:
  - Customers
  - Products
  - Regions
  - Date Table

- Relationships built for optimized filtering and time intelligence

## SHREENSHORT
SALES DASHBOARD:https://github.com/kachiyahiren/D-Mart-Sales-Dashboard/blob/main/Sales%20Dashboard.png

CUSTOMER DASHBOARD:https://github.com/kachiyahiren/D-Mart-Sales-Dashboard/blob/main/Customer%20Dashboard.png

---

## 🧮 Key DAX Measures

```DAX
Total Sales = SUM(Sales[SalesAmount])

Total Profit = SUM(Sales[Profit])

Total Orders = COUNT(Sales[OrderID])

Return Rate =
DIVIDE(
    SUM(Sales[Return Quantity]),
    SUM(Sales[Quantity])
)

YOY Growth % =
DIVIDE(
    [Total Sales] - CALCULATE([Total Sales], SAMEPERIODLASTYEAR(Date[Date])),
    CALCULATE([Total Sales], SAMEPERIODLASTYEAR(Date[Date]))
)

Top Customer =
TOPN(
    1,
    VALUES(Customer[CustomerName]),
    [Total Sales],
    DESC
)# D-Mart-Sales-Dashboard
