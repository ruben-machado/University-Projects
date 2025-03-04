## 📊 **2. Data Warehouse & BI Dashboards**

<div align="center">
  <img src="https://github.com/ruben-machado/University-Projects/blob/main/2.%20Data%20Warehouse%20Design%20and%20Business%20Intelligence%20Dashboarding/Images/Product.png" alt="image alt" width="570" height="420">
</div>

### 🔍 **Overview**

Fabridoce, a company in the food industry, faced challenges in analyzing sales performance, product trends, and overall business metrics efficiently. To address these needs and answer key strategic questions, a Data Warehouse (DW) solution was developed.
This project covers the entire data pipeline process, from data extraction and transformation to loading and reporting. Using Microsoft Fabric, the DW was structured to integrate data from multiple sources, ensuring consistency and reliability. A well-defined ETL process was implemented to clean, transform, and validate data before populating the warehouse.
To support data analysis, a Semantic Model was built, providing a structured framework for querying and generating insights. Finally, a set of reports and dashboards were created using Microsoft Fabric, Power BI Report Builder, and Power BI Desktop, delivering dynamic and interactive visualizations to drive data-driven decision-making.

#### **Note:**

This group project was developed in an academic context as part of the Business Intelligence I & II courses. Some of the data used is artificial or modified for educational purposes. Therefore, no real conclusions or insights should be drawn regarding Fabridoce’s actual sales, business performance, or market context. The objective of this project is to demonstrate the design and implementation of a Data Warehouse, ETL processes, and business intelligence reporting.

### 🛠️ **Tools & Technologies**

- **Data Storage & Management:** Microsoft Fabric Lakehouse, SQL
- **ETL & Data Processing:** Microsoft Fabric Pipelines, Dataflows, Power Query
- **Data Modeling:** Microsoft Fabric Semantic Model, Power BI Desktop
- **Reporting & Visualization:** Power BI Desktop, Microsoft Report Builder, Microsoft Fabric
  
### 📂 **Data Source**

This project used structured B2B sales data (2013–2018) from Fabridoce, provided in Excel (.xlsx) and later split into CSV files. The dataset covered sales transactions, product details, customer segmentation, employee performance, and geographical data across Portugal.

Key attributes included sales quantities, revenue, product hierarchies, pricing, discounts, and commission structures. Clients were categorized by industry (supermarkets, restaurants, hotels, etc.) and company size. Sales trends were analyzed at yearly, monthly, and daily levels.

To meet class requirements, part of the data was artificially generated while maintaining consistency with the original dataset. 

### 🏗️ **Data Warehouse Design**

In data warehousing, dimensions provide descriptive attributes that give context to facts (quantitative data), enabling structured business analysis. As Kimball Group states, “Dimension tables are the soul of the data warehouse”, as they drive the user’s BI experience.

This project follows a Star Schema with one Fact Table and six Dimension Tables, ensuring optimized query performance and ease of analysis. Surrogate keys were introduced in Microsoft Fabric to maintain referential integrity.

<div align="center">
  <img src="https://github.com/ruben-machado/University-Projects/blob/main/2.%20Data%20Warehouse%20Design%20and%20Business%20Intelligence%20Dashboarding/Images/Star_Schema.jpg" alt="image alt" width="550" height="480">
</div>

#### **Dimension Tables**

- dim_date – Captures transaction dates (2013–2018) and supports analysis at daily, weekly, monthly, semester, and yearly levels
- dim_invoice – Stores invoice-related details, including payment methods and invoice categorization for financial insights
- dim_client – Organizes clients by industry (supermarkets, restaurants, etc.) and size (small, medium, large), enabling segmentation and strategic decision-making
- dim_product – Stores product attributes like name, category, unit type, production cost, and pricing, supporting performance analysis
- dim_seller – Contains seller details, including experience, training level, and age (calculated from birthdate during ETL) to analyze sales performance
- dim_location – Provides geographical context, capturing countries, zones, districts, and postal codes of transactions

#### **Fact Table**

The sales_fact_table integrates key business metrics and serves as the central hub of analysis. It contains six foreign keys, linking to each of the dimension tables, and includes essential measures:

- quantity_out – Number of units sold
- sale_amount – Total revenue per transaction
- unit_sale_amount – Revenue per unit sold

###  ⚙️ **ETL Process**

After designing the Data Warehouse, the ETL (Extract, Transform, Load) process was implemented to ensure data integrity and usability. A Lakehouse was created in Fabric to store source data, combining the benefits of data lakes and data warehouses.

Seven CSV files containing raw data were uploaded into LH_SOURCES_FABRIDOCE_SALES. Before integration into the Data Warehouse, transformations were necessary to address missing values, duplicates, incompatible data types, and invalid keys.

#### **Staging Area Warehouse**

A staging area was created with one pipeline and seven distinct dataflows—one for each dimension table and one for the fact table. Each dataflow applied data integrity checks, including:

- Promoting first rows to headers
- Removing duplicates
- Assigning correct data types
- Creating new calculated columns when necessary

The dim_seller table required an extra step: calculating the seller’s age from birthdate. The dim_date table was generated using Power Query, defining the 2013–2018 analysis period and creating relevant time attributes.

<div align="center">
  <img src="https://github.com/ruben-machado/University-Projects/blob/main/2.%20Data%20Warehouse%20Design%20and%20Business%20Intelligence%20Dashboarding/Images/Load_STG_Pipeline.jpg" alt="image alt" width="600" height="450">
</div>

#### **Data Validation Pipeline**

A validation pipeline was implemented to ensure data consistency. Four key rules were applied:

- Rule 1: Check Business Key Integrity – Ensures each dimension table has unique Business Keys
- Rule 2: Check Uniqueness of Attributes – Verifies no duplicate rows exist within dimensions
- Rule 3: Check Integrity of Fact Table PK – Ensures foreign key combinations in the fact table are unique
- Rule 4: Check Foreign Key Relationships – Confirms all fact table references exist in the respective dimension tables

Results were logged in log_quality_checks, recording validation status and identifying potential issues.


<div align="center">
  <img src="https://github.com/ruben-machado/University-Projects/blob/main/2.%20Data%20Warehouse%20Design%20and%20Business%20Intelligence%20Dashboarding/Images/Validate_STG_Pipeline.jpg" alt="image alt" width="900" height="450">
</div>


#### **Loading the Data Warehouse**

After validation, data was loaded into the final Data Warehouse using a structured pipeline:

- Existing data in the DW tables was cleared
- Dimension tables were populated first, with surrogate keys assigned
- Fact table was loaded last, replacing foreign keys with surrogate keys through merges in the dataflow


<div align="center">
  <img src="https://github.com/ruben-machado/University-Projects/blob/main/2.%20Data%20Warehouse%20Design%20and%20Business%20Intelligence%20Dashboarding/Images/Load_DW_Pipeline.jpg" alt="image alt" width="650" height="450">
</div>

#### **Full Load Pipeline & Automation**

A Full Load Pipeline was implemented to automate the entire ETL process:

- Data was loaded into the Staging Area
- Validation checks were executed
- Automated alerts via Outlook and MS Teams notified if errors occurred
- Validated data was transferred into the Data Warehouse
- Final confirmation emails were sent upon success


<div align="center">
  <img src="https://github.com/ruben-machado/University-Projects/blob/main/2.%20Data%20Warehouse%20Design%20and%20Business%20Intelligence%20Dashboarding/Images/Full_Load_Pipeline.jpg" alt="image alt" width="600" height="400">
</div>  
<br>

This structured ETL process ensures data integrity, reliability, and automation, streamlining the transition from raw data to a fully operational Data Warehouse.


### 🧩 **Semantic Model**

After the development of the data warehouse, a semantic model named "SM Fabridoce Sales" was created to support the generation of insightful reports and dashboards. This new model, which is a copy of the original one, enables a structured approach to answering business questions effectively and allows testing transformations, measures, and relationships without affecting the original dataset.

To enhance clarity, dimension tables and variables were renamed, unnecessary attributes were hidden, and hierarchies were established to improve data organization. Additionally, foreign keys (FKs) in the fact table were mapped to their corresponding surrogate keys (SKs) in the dimension tables, ensuring a coherent relational structure.

A crucial step in this process was the development of measures and Key Performance Indicators (KPIs) tailored to business objectives. Using Fabric and Power BI Desktop, various calculated and quick measures were implemented to analyze sales performance, profitability, and market trends.

📌 Fabric Measures:

    Average Sale Amount – Tracks the average selling price of products.
    Gross Profit & Net Profit – Measures profitability before and after expenses.
    KPI Gross Profit Margin – Assesses profitability percentage.
    MoM Revenue Change – Evaluates month-over-month revenue trends.
    Total Sales & Expenses – Provides insights into revenue and cost structure.

📌 Power BI Measures:

    Market Share % – Determines each product's contribution to total sales.
    Sales Growth % (2017-2018) – Measures year-over-year sales performance.

### 📊 **Reports and Dashboards**

Following the establishment of the semantic model, a total of six reports were developed to effectively address the business problem. 
This includes four paginated reports, two created in Microsoft Fabric and two in Power BI Report Builder, providing structured, table-based insights.

Additionally, two interactive dashboard-style reports were designed using Microsoft Power BI Desktop, using advanced analytical features for exploration of the Fabridoce case. Each Power BI report consists of three pages:

- **Products Report: Covers Sales Overview, Product Performance, and Top 5 Products**

<div align="center">
  <img src="https://github.com/ruben-machado/University-Projects/blob/main/2.%20Data%20Warehouse%20Design%20and%20Business%20Intelligence%20Dashboarding/Dashboards%20and%20Reports/Sales_Overview.png" alt="image alt" width="900" height="500">
</div>  
<br>


<div align="center">
  <img src="https://github.com/ruben-machado/University-Projects/blob/main/2.%20Data%20Warehouse%20Design%20and%20Business%20Intelligence%20Dashboarding/Dashboards%20and%20Reports/Products_Performance.png" alt="image alt" width="900" height="500">
</div> 
<br>


<div align="center">
  <img src="https://github.com/ruben-machado/University-Projects/blob/main/2.%20Data%20Warehouse%20Design%20and%20Business%20Intelligence%20Dashboarding/Dashboards%20and%20Reports/Top_5_Products_2018.png" alt="image alt" width="900" height="500">
</div> 

<br>

- **Sellers, Clients, and Locations Report: Focuses on Sellers' Info, Clients, and Locations**

<div align="center">
  <img src="https://github.com/ruben-machado/University-Projects/blob/main/2.%20Data%20Warehouse%20Design%20and%20Business%20Intelligence%20Dashboarding/Dashboards%20and%20Reports/Sellers'_info.png" alt="image alt" width="900" height="500">
</div> 
<br>


<div align="center">
  <img src="https://github.com/ruben-machado/University-Projects/blob/main/2.%20Data%20Warehouse%20Design%20and%20Business%20Intelligence%20Dashboarding/Dashboards%20and%20Reports/Clients.png" alt="image alt" width="900" height="500">
</div> 
<br>


<div align="center">
  <img src="https://github.com/ruben-machado/University-Projects/blob/main/2.%20Data%20Warehouse%20Design%20and%20Business%20Intelligence%20Dashboarding/Dashboards%20and%20Reports/Location.png" alt="image alt" width="900" height="500">
</div> 
<br>

These reports offer a structured and interactive approach to analyzing sales, product performance, and customer data, supporting data-driven decision-making.

For more details about the project, check the Report PDF, which provides an in-depth explanation of the process, methodologies, and findings.

