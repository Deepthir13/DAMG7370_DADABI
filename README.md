# 🚔 NYPD Crime Analysis – End-to-End BI Pipeline

**🔧 Built using Alteryx, Snowflake, Azure Data Factory, and Tableau**

---

## 📝 Project Overview

This project showcases my ability to build a **full-scale business intelligence solution** from raw public safety data. Leveraging the **NYPD Arrests Dataset**, I designed an end-to-end pipeline to transform, model, and visualize criminal trends across New York City.

---

## 🎯 Objectives

- Transform and clean raw arrest records  
- Model structured data into a star schema using **Snowflake**  
- Automate data loading with **Azure Data Factory** pipelines  
- Deliver powerful insights via **Tableau dashboards**

---

## 🛠️ Tools & Technologies

| Layer           | Tools Used                                  |
|-----------------|----------------------------------------------|
| Cleaning        | Alteryx                                      |
| Cloud Storage   | Snowflake                                    |
| Pipelines       | Azure Data Factory (ADF)                     |
| Data Modeling   | ER/Studio, SQL                               |
| BI & Reporting  | Tableau                                      |
| Scripting       | SQL, ETL Logic, DDL                          |

---

## 🗃️ Dataset Info

- **Source**: NYPD Arrests Public Dataset  
- **Size**: ~260K rows × 19 columns  
- **Grain**: One row per arrest record  
- **Attributes**: Arrest Date, Crime Type, Borough, Age, Gender, etc.

---

## 🧱 Data Warehouse Schema

Star Schema Implementation in Snowflake:

**🔹 Fact Table**  
- `Arrest_Fact`: Central table containing arrest transactions  

**🔹 Dimension Tables**  
- `DIM_Time`: Day, Month, Year  
- `DIM_Crime`: PD Code, Offense Category  
- `DIM_Location`: Borough, Precinct, Latitude/Longitude  
- `DIM_Preperator`: Demographics like Age, Gender, Race

---

## 🔄 Data Transformation Highlights

| Task               | Description                                         |
|--------------------|-----------------------------------------------------|
| Null Handling       | Cleaned missing coordinates and crime codes        |
| Type Conversion     | Casted dates, numerics, and flags into correct types |
| Filtering           | Removed non-NYC jurisdiction arrests               |
| Enrichment          | Created Age Buckets and Geo Reference columns      |
| Imputation          | Replaced missing geolocation values with means     |

---

## 📊 Tableau Dashboards Overview

### 📅 Time Trend Analysis  
- Arrest patterns by year, quarter, month  
- Identified peak periods (e.g., March 14, Summer months)

### 🚨 Crime Categories  
- Top 5 crimes: Assault, Larceny, Drug Possession  
- Long-term trend visualizations  

### 🗺️ Geographic Heatmaps  
- Borough-wise and precinct-level crime densities  
- Highlighted high-arrest zones like Brooklyn, Manhattan  

### 🧑 Demographic Patterns  
- Arrestee distribution by age, gender, and race  
- Most common profile: Age 18–25, Male, Black/Hispanic

### 🔮 Predictive Visuals  
- Hotspot forecasts based on historic seasonality  
- Summer months show consistent spikes

---

## 💾 Fact Table Sample DDL

```sql
CREATE TABLE Arrest_Fact (
  ARREST_KEY VARCHAR(10) NOT NULL,
  PD_CD_SK INT NOT NULL,
  ARREST_PRECINCT_SK INT NOT NULL,
  DATE_SK CHAR(10) NOT NULL,
  PREP_ID_SK INT NOT NULL,
  PRIMARY KEY (ARREST_KEY, PD_CD_SK, ARREST_PRECINCT_SK, DATE_SK, PREP_ID_SK)
);
```

## 📌 Business Questions Answered

| Question                                           | Addressed In             |
|----------------------------------------------------|---------------------------|
| What are the seasonal arrest trends?              | Time-Based Dashboard      |
| Which crimes are increasing or decreasing?        | Category Trends           |
| Which areas are crime hotspots?                   | Geographic Visualizations |
| What are the common profiles of arrestees?        | Demographics View         |
| Can we forecast high-risk periods/areas?          | Predictive Heatmaps       |

---

## 🚀 How I Built This

```bash
1. Clean raw CSV in Alteryx – handle nulls, add derived fields
2. Upload processed data to Snowflake (Bronze Layer)
3. Design Star Schema using ER/Studio
4. Load fact/dim tables using ADF pipelines (Silver → Gold)
5. Connect Tableau to Snowflake and build 5 dashboards
```

## 💡 Key Takeaways

- 🏗️ Built scalable ETL using **Azure Data Factory + Snowflake**  
- 🧠 Modeled a real-world star schema from semi-structured data  
- 📊 Designed dashboards that deliver insight, not just visuals  
- 🧹 Gained hands-on experience with **Alteryx** for fast transformations  
- 📌 Sharpened SQL skills for optimized queries and DDL scripting  

---

## 📌 Why This Project Matters

This project proves my capability to **own the full BI pipeline** — from raw messy files to polished dashboards.  
It's a demonstration of how I can clean, model, and visualize data at scale with **cloud-native tools**.


---
