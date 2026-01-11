# 📊 Adventure Works (AW) – Power BI Dashboard Project

## 📌 Project Overview

This project is an **end-to-end Business Intelligence dashboard** built using **Power BI**, with **Excel as the data source**.
The goal of this project is to transform raw sales data into **interactive, insight-driven dashboards** using **ETL, star schema data modeling, DAX measures, and advanced Power BI features**.

The dashboard provides deep insights into **sales performance, product categories, customer behavior, and regional trends** for the Adventure Works business.

---

## 🗂️ Data Source

* **Excel File:** `data.xlsx`
* The Excel file contains structured datasets used for analysis.
* Data was imported into Power BI and transformed using **Power Query**.

---

## 🔄 ETL PROCESS (Extract – Transform – Load)

### Extract

* Imported Excel data (`data.xlsx`) into Power BI.
* Loaded multiple tables related to sales, products, customers, dates, and territories.

### Transform (Power Query)

* Cleaned raw data:

  * Removed unnecessary columns
  * Handled missing and inconsistent values
  * Standardized data types (dates, numeric fields)
* Created calculated columns:

  * Year, Quarter, Month
  * Profit and Profit Margin
* Renamed columns for clarity and business readability

### Load

* Loaded clean, transformed data into the Power BI data model.
* Prepared datasets for reporting and analysis.

---

## 🧩 DATA MODELING

A **star schema data model** was implemented to ensure optimal performance and accurate filtering.

### Fact Table

* **Sales Data**

  * Sales Amount
  * Units Sold
  * Profit
  * Order and Ship Dates
  * Product, Customer, and Territory keys

### Dimension Tables

* **Date**
* **Product**
* **Category**
* **SubCategory**
* **Customer**
* **Territory**

### Modeling Highlights

* One-to-many relationships between dimension tables and fact table
* Single-direction filtering to avoid ambiguity
* Date table enabled for time-based analysis
* Model optimized for slicers and drill-down analysis

---

## 📈 DASHBOARD OVERVIEW (Report Name: **AW**)

### 🏠 Landing Page

* High-level KPIs:

  * Total Sales
  * Total Profit
  * Customer Count
  * Profit Margin %
* Navigation buttons to move across report pages
* Designed as an executive summary entry point

---

### 📊 Sales Overview Page

**Purpose:** Monitor overall business performance

**Key Metrics & Visuals**

* Total Sales by Year
* Total Sales by Quarter
* Total Sales by Month
* Country-wise Sales by Year
* KPI cards for Sales, Profit, Products, Margin

**Features**

* Filters for Product, Category, Subcategory, Country
* Interactive slicers for dynamic analysis

---

### 🛒 Product Performance Page

**Purpose:** Analyze product and category contribution

**Visuals**

* Total Sales by Category
* Total Sales by Sub-Category
* Product-level sales comparison

**Insights**

* Identifies top-performing and underperforming categories
* Highlights revenue concentration across bike types

---

### 🚴 Product Deep-Dive Pages

Separate detailed pages created for:

* **Road Bikes**
* **Touring Bikes**
* **Mountain Bikes**

**Each page includes:**

* Sales, Profit, Margin %, Customers, Units Sold
* Sales trend by Year
* Sales & Profit by Country
* Sales by Education / Occupation / Marital Status
* Top customers and top products

---

## 🎛️ INTERACTIVITY & ADVANCED FEATURES

* **Slicers** for:

  * Gender
  * Product
  * Category
  * Subcategory
  * Country
* **Report-level and page-level filters**
* **Tooltips** for enhanced data context
* **Navigation buttons** (Back / Next) for smooth user experience
* Cross-filtering enabled across all visuals

---

## 📐 DAX MEASURES USED (Examples)

* Total Sales
* Total Profit
* Profit Margin %
* Customer Count
* Units Sold

### 🔹 Total Sales

Calculates total revenue from sales transactions.

```DAX
Total Sales = 
SUM ( 'Sales Data'[SalesAmount] )
```

---

### 🔹 Total Profit

Measures overall profitability.

```DAX
Total Profit = 
SUM ( 'Sales Data'[Profit] )
```

---

### 🔹 Profit Margin %

Evaluates business efficiency and margin health.

```DAX
Profit Margin % = 
DIVIDE ( [Total Profit], [Total Sales], 0 )
```

---

### 🔹 Customer Count

Counts unique customers contributing to sales.

```DAX
Customer Count = 
DISTINCTCOUNT ( 'Sales Data'[CustomerKey] )
```

---

### 🔹 Total Units Sold

Calculates the total number of products sold.

```DAX
Total Units Sold = 
SUM ( 'Sales Data'[OrderQuantity] )
```

---

### 🔹 Total Products

Counts unique products sold.

```DAX
Total Products = 
DISTINCTCOUNT ( 'Sales Data'[ProductKey] )
```

---

### 🔹 Total Production Cost

Calculates total cost incurred for product sales.

```DAX
Total Production Cost = 
SUM ( 'Sales Data'[ProductStandardCost] )
```

---

## 🚴 Category-Specific DAX Measures

Used for **Road Bike, Touring Bike, and Mountain Bike** drill-down pages.

---

### 🔹 Road Bike Sales

```DAX
Road Sales =
CALCULATE (
    [Total Sales],
    'SubCategory'[SubCategoryName] = "Road Bikes"
)
```

---

### 🔹 Road Bike Profit

```DAX
Road Profit =
CALCULATE (
    [Total Profit],
    'SubCategory'[SubCategoryName] = "Road Bikes"
)
```

---

### 🔹 Road Bike Margin %

```DAX
Road Margin % =
DIVIDE ( [Road Profit], [Road Sales], 0 )
```

---

### 🔹 Touring Bike Sales

```DAX
Touring Sales =
CALCULATE (
    [Total Sales],
    'SubCategory'[SubCategoryName] = "Touring Bikes"
)
```

---

### 🔹 Mountain Bike Sales

```DAX
Mountain Sales =
CALCULATE (
    [Total Sales],
    'SubCategory'[SubCategoryName] = "Mountain Bikes"
)
```

---

## 📅 Time Intelligence DAX

Used in **Year, Quarter, and Month trend analysis**.

---

### 🔹 Sales by Year

```DAX
Sales by Year =
CALCULATE (
    [Total Sales],
    VALUES ( 'Date'[CalendarYear] )
)
```

---

### 🔹 Sales by Month

```DAX
Sales by Month =
CALCULATE (
    [Total Sales],
    VALUES ( 'Date'[MonthName] )
)
```
DAX was used to create reusable, scalable business metrics across all pages.

---

## 🛠️ Tools & Technologies

* **Power BI**

  * Power Query
  * Data Modeling
  * DAX
  * Interactive Visuals
* **Microsoft Excel**

  * Source data preparation

---

## 🧠 Key Learnings

* Practical ETL using Power Query
* Real-world star schema data modeling
* Writing optimized DAX measures
* Designing business-focused dashboards
* Creating user-friendly navigation and storytelling dashboards

---

## 🚀 Conclusion

This project demonstrates the ability to build **enterprise-level BI dashboards** using **Power BI with Excel data**, following industry-standard analytics practices.

It reflects strong skills in:

* Data preparation
* Modeling
* Visualization
* Business insight generation

---

## 📬 Feedback & Opportunities

Feedback is welcome.
Open to **Data Analyst / Business Analyst / Power BI Developer roles**.

# Screenshots / Demos

![Dashboard View](https://github.com/Keerthana-duraipandian/Adventure-Works-AW-Power-BI-Dashboard-Project/blob/main/Coverpage__bike_DB.png)

![Dashboard View](https://github.com/Keerthana-duraipandian/Adventure-Works-AW-Power-BI-Dashboard-Project/blob/main/Sales_bike_DB.jpeg)

![Dashboard View](https://github.com/Keerthana-duraipandian/Adventure-Works-AW-Power-BI-Dashboard-Project/blob/main/Coverpage__bike_DB.png)

![Dashboard View](https://github.com/Keerthana-duraipandian/Adventure-Works-AW-Power-BI-Dashboard-Project/blob/main/Cat_Subcat.jpeg)

![Dashboard View](https://github.com/Keerthana-duraipandian/Adventure-Works-AW-Power-BI-Dashboard-Project/blob/main/Road_bike_DB.jpeg)

![Dashboard View](https://github.com/Keerthana-duraipandian/Adventure-Works-AW-Power-BI-Dashboard-Project/blob/main/Tour_bike_DB.jpeg)

![Dashboard View](https://github.com/Keerthana-duraipandian/Adventure-Works-AW-Power-BI-Dashboard-Project/blob/main/Mountain_bike_DB.jpeg)




