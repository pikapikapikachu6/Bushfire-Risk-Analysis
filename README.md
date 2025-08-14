# Bushfire Risk Analysis – Spatial Database & GIS Data Integration

## 📌 Overview
This project implements a **spatial database system** for analysing bushfire risk across Greater Sydney, integrating **multi-source GIS shapefiles** and **statistical datasets**.  
It was developed as part of the DATA2001 Practical Assignment at the University of Sydney and demonstrates expertise in **PostgreSQL + PostGIS**, **Python data processing**, **SQL query optimization**, and **interactive geospatial visualization**.

The system computes a composite **Bushfire Risk Score** using demographic, environmental, and infrastructure datasets, enabling spatial analysis and visualisation for informed decision-making.

---

## 🚀 Key Features
- **PostgreSQL + PostGIS Spatial Database**  
  Integrated multiple datasets, including CSV and Shapefiles, with support for spatial indexing and geometry operations.

- **Data Cleaning & Preprocessing**  
  - Python-based ETL (Extract, Transform, Load) pipeline using **Pandas** and **GeoPandas**.  
  - Automated handling of missing values, data type conversion, and geometry standardization.

- **Database Design & Optimization**  
  - Implemented **primary keys**, **foreign keys**, **normal indexes**, and **spatial indexes**.  
  - Optimized queries for faster spatial data retrieval.

- **Geospatial Analysis**  
  - Used **JOIN** and **SPATIAL JOIN** to link demographic, business, vegetation, and waterbody datasets.  
  - Applied **z-score normalization**, **weighted averages**, and **sigmoid functions** to calculate a composite fire risk score.

- **Interactive Visualization**  
  - Generated zoomable maps to display neighbourhood-level risk scores.  
  - Risk intensity is color-coded for easy interpretation.

- **Data Integrity & Security Principles**  
  - Enforced referential integrity via constraints.
  - Designed database schema following **secure software design** practices.

---

## 🛠️ Technology Stack
- **Languages:** Python, SQL
- **Database:** PostgreSQL, PostGIS
- **Libraries:** Pandas, GeoPandas, Matplotlib
- **Data Sources:** Government GIS datasets, statistical CSV datasets
- **Tools:** QGIS (for spatial data inspection), pgAdmin

---

## 📊 Dataset Summary
| Dataset Name | Format | Description |
|--------------|--------|-------------|
| StatisticalAreas | CSV | Area identifiers and parent area references |
| Neighbourhoods | CSV | Census data (population, dwellings, etc.) |
| BusinessStats | CSV | Number of businesses by category |
| RFSNSW_BFPL | SHP | Vegetation coverage and categories |
| SA2_2016_AUST | SHP | Australian Statistical Geography Standard regions |
| Lakes | SHP | Waterbodies in Greater Sydney |

---

## 🔍 Analysis Methodology
1. **Import & Preprocessing**
   - Loaded CSV files with Python, Shapefiles with PostGIS.
   - Standardized geometry type to `MULTIPOLYGON` (SRID 4283).

2. **Database Linking**
   - Joined datasets using `area_id` and spatial joins on geometry fields.
   - Created indexes to improve query performance.

3. **Risk Calculation**
   - Formula:
     ```
     Risk = sigmoid(
         z(pop_density) + 
         z(dwelling_business_density) + 
         z(vegetation_density) -
         z(assistive_service_density) -
         z(lake_density)
     )
     ```
   - Added lake density as a mitigating factor for bushfire risk.

4. **Visualization**
   - Plotted interactive maps showing risk intensity.
   - Analyzed correlations between risk score, income, and rental prices.

---

## 📌 Skills Demonstrated
- Advanced **SQL** and **PostGIS** spatial operations
- **Database schema design** and query optimization
- **Geospatial data integration** from multiple sources
- **Data cleaning** and ETL with Python
- **Interactive data visualization**
- Application of **secure software design** and data integrity principles

---
