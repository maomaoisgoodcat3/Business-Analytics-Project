# Grocery Sales Intelligence: End-to-End BI Project

**Author:** Pham Huu Manh  
**Tool Stack:** Power BI, Power Query (M Code), DAX, Data Modeling (Star Schema)

## Project Overview
This project transforms a raw, relational Grocery Sales dataset (sourced from Kaggle by Andrex Ibiza[cite: 7, 8]) into an interactive Business Intelligence solution. Spanning transactional data from January to May 2018[cite: 7, 8], the goal is to provide actionable insights across product management, customer retention, and operational efficiency[cite: 8]. 

The dashboard addresses five core business objectives[cite: 7, 8]:
1. **Monthly Sales Performance:** Tracking revenue trends and MoM/WoW growth.
2. **Top Products Identification:** Applying Pareto (80/20) principles to rank and classify core products.
3. **Customer Purchase Behavior:** Segmenting customers using a custom RFM (Recency, Frequency, Monetary) approach.
4. **Salesperson Effectiveness:** Establishing baselines to evaluate employee revenue generation.
5. **Geographical & Operational Insights:** Analyzing transaction density by time-bins for better staff allocation.

---

## Data Pipeline & Methodology

### 1. ETL Process (Power Query)
The raw dataset contained structural inconsistencies that were resolved using Power Query (M Code)[cite: 8]:
*   **Data Cleaning:** Addressed issues such as `$0` `TotalPrice` records by recalculating actual revenue using merged product prices[cite: 8].
*   **Column Splitting & Merging:** Separated `SalesDate` into distinct Date and Time columns[cite: 8], grouped times into operational bins (`Sales Time (bins)`)[cite: 8]. Consolidated fragmented name columns (`FirstName`, `MiddleInitial`, `LastName`) into a single `FullName` column for Customers and Employees[cite: 8].
*   **Date Dimension:** Dynamically generated a comprehensive `Dim_Date` table using M Code to support Time Intelligence calculations[cite: 7, 8].

### 2. Data Modeling
The data was restructured from a normalized state into a highly optimized **Star Schema**[cite: 7, 8]. Extraneous tables (like raw categories, cities, countries) were hidden or merged to streamline the model[cite: 8], leaving a central `Fact_Sales` table surrounded by conformed dimensions (`Dim_Customers`, `Dim_Products`, `Dim_Employees`, `Dim_Date`)[cite: 7, 8].

### 3. DAX Measures & Analytics
A dedicated `KeyMeasures` table was created to house complex DAX calculations[cite: 7], including[cite: 8]:
*   **RFM Customer Segmentation:** Calculated `R_Recency`, `F_Frequency`, and `M_Monetary` columns to classify customers into segments like *Loyal*, *New*, or *VIP At Risk*[cite: 7, 8].
*   **Advanced Metrics:** `Pareto Cumulative %`, `MoM/WoW/DoD Growth %`, `Average Order Value (AOV)`, and `Avg Transactions per Bin`[cite: 8].

---

## Dashboard Preview

*(Insert screenshots of your Power BI Dashboard here)*

![Dashboard Main View]([Link-To-Your-Image])  
*Caption: Overview of the Grocery Sales Performance.*

---

## How to Explore This Project

### Option 1: View the Final Report (Quickest)
You can review the comprehensive project report detailing the ETL process, schema design, and DAX logic in the provided PDF:
*   📄 **[ReportFinalExam.pdf](./ReportFinalExam.pdf)**[cite: 8]
*   📄 **[Slide_for_Representation.pdf](./Slide_for_Representation.pdf)**[cite: 7]

### Option 2: Explore the Interactive Dashboard (Power BI Desktop Required)
To interact with the data, drill down into specific metrics, and view the DAX code:
1. Ensure you have [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) installed.
2. Clone or download this repository.
3. Open the `.pbix` file located in the root directory.
4. Navigate through the tabs to explore different business insights. Click on visuals to cross-filter the data.

---
*This project was completed as part of the Business Intelligence final examination.*[cite: 7, 8]
