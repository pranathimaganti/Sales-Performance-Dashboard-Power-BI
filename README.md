# Sales Performance & Trend Analysis Dashboard (Power BI)

## Project Overview
This project involves the design and development of an **enterprise-grade Power BI dashboard** to analyze sales performance and trends for a business.  
The dashboard enables stakeholders to monitor key metrics such as **Sales, Profit, Quantity**, track **time-based trends**, compare **categories and regions**, and support **data-driven decision-making**.

---

## Business Objectives
- Analyze overall **Sales, Profit, and Quantity**
- Track **monthly and yearly trends**
- Compare performance across **categories, products, and regions**
- Compare **actual performance vs targets**
- Enable **interactive exploration** using slicers and dashboards

---

## Data Sources
The project uses Excel files as the primary data source:

- **Sales.xlsx** – Fact table containing transactional sales data  
- **Targets.xlsx** – Target values for performance comparison  
- **DimDate** – Calendar table for time intelligence  
- **DimProduct** – Product details  
- **DimCustomer** – Customer details  
- **DimRegion** – Geographic information  

---

## Data Transformation (Power Query)
Data preparation was performed using **Power Query Editor**, including:
- Removal of null values and duplicates
- Correct data type assignment
- Splitting columns (e.g., Region into Country/State)
- Creating **conditional columns** (High / Medium / Low sales)
- Ensuring clean, analysis-ready datasets

---

## Data Model Design
The data model follows a **Star Schema** design.

### Central Fact Table
- **FactSales**

### Dimension Tables
- **DimDate**
- **DimProduct**
- **DimCustomer**
- **DimRegion**
- **Targets**

### Relationships Added
- FactSales[OrderDate] → DimDate[Date]
- FactSales[ProductID] → DimProduct[ProductID]
- FactSales[CustomerID] → DimCustomer[CustomerID]
- FactSales[Category] → Targets[Category]
- FactSales[Country] → DimRegion[Country]

All relationships are:
- One-to-many
- Single-direction
- Active  
DimDate is marked as the **Date Table**.

---

## DAX Measures
Key measures were created using **DAX** for accurate and reusable calculations.

### Core Measures
- Total Sales  
- Total Profit  
- Total Quantity  

### Time Intelligence Measures
- Sales YTD  
- Sales Last Year (LY)  
- Year-over-Year (YoY) Growth %

These measures enable trend analysis and performance comparison over time.

---

## Report Pages & Visualizations

### Page 1: Executive Dashboard
- KPI Cards: Total Sales, Total Profit, YoY Growth %
- Donut Chart: Sales by Category
- Ribbon Chart: Category Rank Over Time
- Line Chart: Monthly Sales Trend

### Page 2: Trend Analysis
- Line Chart: Sales & Profit Trends
- Line + Stacked Column Chart: Actual vs Target
- Regional analysis using alternative visuals (bar/treemap)  
  *(Map visuals were restricted due to tenant security settings)*

### Page 3: Product Performance
- Matrix: Category → Subcategory → Product
- Conditional formatting (data bars, color scales)
- Top-N analysis
- Report-level slicers:
  - Year
  - Category
  - Country

---

## Filters & Interactivity
- Report-level slicers applied across all pages
- Drill-down enabled in matrix visuals
- Page navigation implemented using **action buttons**

---

## Dashboard Creation (Power BI Service)
- Report published to **Power BI Service**
- Key visuals pinned to a single dashboard:
  **Sales Performance Dashboard**
- Dashboard provides a **one-page executive summary**
- KPI alerts configured / explained conceptually due to account limitations

---

## Q&A Visual
- Q&A visual added to allow **natural language querying**
- Enables users to ask questions like:
  - “Total sales by category”
  - “Total profit by year”

---

## Advanced Visuals (R Script)
- R script visuals were explored to demonstrate advanced analytics integration
- Due to dataset and environment constraints, the R visual was documented conceptually
- This step demonstrates awareness of Power BI’s extensibility using R

---

## Tools Used
- Power BI Desktop
- Power BI Service
- Microsoft Excel
- DAX
- Power Query
- R (conceptual integration)

---

