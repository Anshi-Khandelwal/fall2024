# 🚦 Collision Analytics – Motor Vehicle Crash Intelligence Platform

## 📌 Project Overview
This project delivers an **end-to-end analytics and business intelligence pipeline** for analyzing **motor vehicle collision data** across **New York City, Chicago, and Austin**.

The goal was to design a **scalable data architecture** that transforms raw, heterogeneous crash datasets into **analytics-ready dimensional models** and **actionable dashboards** to support safety analysis and decision-making.

The solution processes **5M+ collision records** and demonstrates skills in **data profiling, ETL orchestration, dimensional modeling, performance optimization, and visualization**.

---

## 🗂️ Data Sources
Collision data was sourced from official city and DOT open-data portals:

- **NYC:** Motor Vehicle Collisions – Crashes (NYC Open Data)
- **Chicago:** Traffic Crashes – Crashes (Chicago Data Portal)
- **Austin:** Crash Report Data – Crash Level Records (Texas DOT)
- **Montgomery:**

Each city dataset had **different schemas, formats, and data quality issues**, requiring standardization before integration.

---

## 🔍 Data Profiling & Quality Assessment
Before building ETL pipelines, extensive **data profiling** was performed using **Alteryx** to assess data quality and identify anomalies.

<img width="742" height="236" alt="image" src="https://github.com/user-attachments/assets/5649c53b-1eaa-4e27-85c5-2a06059c1462" />

Key checks included:
- Missing and null value analysis
- Invalid or inconsistent geographic coordinates
- Date and time inconsistencies
- Severity and injury-related anomalies
- Schema mismatches across cities

Profiling results directly informed:
- Cleaning and standardization logic in Talend
- Rejection and filtering rules
- Source-to-target transformation mappings

---

## 🔄 ETL & Pipeline Architecture

### 🧩 Staging Layer – Azure Data Factory (ADF)
Azure Data Factory was used to orchestrate:
- Ingestion of raw city datasets
- Loading data into Snowflake staging tables
- Parquet-based intermediate storage for performance optimization

ADF best practices applied:
- Parameterized pipelines
- Reusable datasets
- Row-count validation and reconciliation

<img width="800" height="364" alt="image" src="https://github.com/user-attachments/assets/88f5fa99-1292-4bda-a9a5-6118fb68171c" />

ADF artifacts are organized under:
- `dataflow/`
- `dataset/`
- `pipeline/`
- `factory/`
- `linkedService/`
- `integrationRuntime/`

---

### 🔧 Transformation Layer – Talend
Talend was used for:
- Data cleaning and normalization
- Source-to-target transformations
- Building fact and dimension datasets

Included in this repository:
- Representative Talend **process job definitions** (`.item`, `.properties`)

Excluded intentionally:
- Environment-specific context files
- Credentials and runtime configurations

<img width="800" height="346" alt="image" src="https://github.com/user-attachments/assets/9bc54038-24fc-4cd3-8b16-8f1f976ee929" />

---

## 🧱 Dimensional Data Model
A **star schema** was designed using **ER/Studio / Navicat**, consisting of **10+ tables**, including:

- **Fact Table:** Collision / Accident Events
- **Dimension Tables:** Location, Time, Source, Contributor, Severity, and others

The model supports:
- City-level and overall reporting
- Time-based and seasonal analysis
- Injury and fatality analysis
- High-performance BI queries

A detailed **mapping document** was created to document:
- Source column → target column mappings
- Transformation rules
- Audit and validation logic

<img width="468" height="385" alt="image" src="https://github.com/user-attachments/assets/103c679b-4ba5-496a-9171-b1bb7e8ad96e" />


---

## ⚡ Performance Optimization
To improve scalability and efficiency:
- Snowflake storage was optimized using **Parquet**
- Storage footprint reduced by **~60%**
- End-to-end data processing improved by **~40%**

---

## 📊 Analytics & Visualizations
Dashboards were developed using **Power BI (and Tableau)** to answer key business questions, including:

- Total number of accidents by city and overall
- Top accident-prone areas (Top 3 / Top 5 by city)
- Injury-only vs fatal accidents
- Pedestrian involvement (Chicago-specific analysis)
- Time-based trends (hour of day, weekday vs weekend)
- Seasonal accident patterns
- Key contributing factors in accidents

📁 **Repository Note**  
This repository includes a **summarized visualization PDF**.  
The complete set of dashboards and supporting artifacts are shared via Dropbox.

<img width="400" height="223" alt="image" src="https://github.com/user-attachments/assets/49dfda64-2971-42e9-9ca1-4aae94b5f5d2" />

---
### 🛠️ Skills & Tools Demonstrated
- **ETL & Orchestration:** Azure Data Factory, Talend
- **Data Profiling:** Alteryx
- **Data Modeling:** ER/Studio, Navicat
- **Data Processing:** Python
- **Data Warehouse & Storage:** Snowflake, Parquet
- **Visualization:** Power BI, Tableau
---


## ✅ Key Outcomes
- Processed **5M+ collision records** across three cities
- Built a **scalable BI architecture** from raw data to dashboards
- Improved data processing performance by **~40%**
- Reduced storage footprint by **~60%**
- Delivered actionable insights for traffic safety analysis

---

## 🔒 Notes on Security & Data Size
- Raw datasets and large profiling outputs are excluded from GitHub
- No credentials or environment-specific configuration files are included
- Full artifacts are shared securely via Dropbox for interview review

## 📂 Repository Structure

```text
FinalProject/
├── dataflow/               # Azure Data Factory data flows
├── dataset/                # Azure Data Factory datasets
├── pipeline/               # Azure Data Factory pipelines
├── factory/                # Azure Data Factory factory metadata
├── linkedService/          # Azure Data Factory linked services
├── integrationRuntime/     # Azure Data Factory integration runtime
├── talend/
│   └── process/            # Talend transformation jobs
├── visualizations/         # Dashboard summaries
└── README.md
