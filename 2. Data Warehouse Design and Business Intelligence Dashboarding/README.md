## 📊 **2. Data Warehouse Design and Business Intelligence Dashboarding**

### 🔍 **Overview**


### 🛠️ **Tools & Technologies**

- **Data Visualization Software**: 
- **Data Analysis**: 
- **Visualizations**:
  
### 📂 **Data Source**

This project used structured B2B sales data (2013–2018) from Fabridoce, provided in Excel (.xlsx) and later split into CSV files. The dataset covered sales transactions, product details, customer segmentation, employee performance, and geographical data across Portugal.

Key attributes included sales quantities, revenue, product hierarchies, pricing, discounts, and commission structures. Clients were categorized by industry (supermarkets, restaurants, hotels, etc.) and company size. Sales trends were analyzed at yearly, monthly, and daily levels.

To meet class requirements, part of the data was artificially generated while maintaining consistency with the original dataset. 

### 🛠️ **Data Warehouse Design**

In data warehousing, dimensions provide descriptive attributes that give context to facts (quantitative data), enabling structured business analysis. As Kimball Group states, “Dimension tables are the soul of the data warehouse”, as they drive the user’s BI experience.

This project follows a Star Schema with one Fact Table and six Dimension Tables, ensuring optimized query performance and ease of analysis. Surrogate keys were introduced in Microsoft Fabric to maintain referential integrity.

#### **Dimension Tables**

- dim_date – Captures transaction dates (2013–2018) and supports analysis at daily, weekly, monthly, semester, and yearly levels.
- dim_invoice – Stores invoice-related details, including payment methods and invoice categorization for financial insights.
- dim_client – Organizes clients by industry (supermarkets, restaurants, etc.) and size (small, medium, large), enabling segmentation and strategic decision-making.
- dim_product – Stores product attributes like name, category, unit type, production cost, and pricing, supporting performance analysis.
- dim_seller – Contains seller details, including experience, training level, and age (calculated from birthdate during ETL) to analyze sales performance.
- dim_location – Provides geographical context, capturing countries, zones, districts, and postal codes of transactions.

#### **Fact Table**

The sales_fact_table integrates key business metrics and serves as the central hub of analysis. It contains six foreign keys, linking to each of the dimension tables, and includes essential measures:

- quantity_out – Number of units sold.
- sale_amount – Total revenue per transaction.
- unit_sale_amount – Revenue per unit sold.

### 🚀 **Key Findings**
