# Agriculture Productivity Analysis Dashboard  

---

## Dashboard Link  

**Live Report:**  
https://app.powerbi.com/view?r=eyJrIjoiNGVjYTkzNjEtNzU1ZS00Zjg5LWFmNzAtOGY4NDIyYzE1ZjlmIiwidCI6ImNlOTAwODg5LTY5NTctNDJlMy04NWNlLTQwNTQyMzZiNjNiZCJ9  

---

## Project Overview  

This project analyzes **agricultural productivity** by evaluating environmental factors such as **rainfall, temperature, and humidity** across crops, regions, seasons, and years.  

The goal is to enable **data-driven crop planning and strategic agricultural decision-making** through interactive analytics.

---

## Core Objectives  

- Identify **highest yielding crops**
- Compare **regional agricultural performance**
- Analyze **seasonal productivity variations**
- Detect **year-wise yield fluctuations**
- Understand **environmental impact on crop output**

---

## Tech Stack  

| Layer | Technology |
|-------|------------|
| Data Storage | Amazon S3 |
| Data Warehouse | Snowflake |
| Data Transformation | Snowflake SQL |
| Visualization | Power BI Desktop |
| Deployment | Power BI Service |
| Analytics | DAX |

---

## Data Engineering Pipeline  

1. Created **Amazon S3 bucket** and uploaded raw dataset  
2. Configured **IAM Role** for Snowflake–S3 integration  
3. Created **Integration Object in Snowflake**  
4. Loaded dataset into Snowflake from S3  
5. Performed **data validation and SQL transformations**  
6. Created calculated column **"Rainfall Groups"**  
7. Imported transformed dataset into **Power BI Desktop**  
8. Published report to **Power BI Service**

---

## Data Modeling  

### Calculated Column (Snowflake SQL)

**Rainfall Groups Classification**

- 255 – 1200 → **Low**
- 1200 – 2800 → **Medium**
- 2800 – 4103 → **High**

---

### DAX Measures Created  

```DAX
Total Yield = SUM(Agriculture[Yield])

Avg Rainfall = AVERAGE(Agriculture[Rainfall])

Avg Temperature = AVERAGE(Agriculture[Temperature])

Avg Humidity = AVERAGE(Agriculture[Humidity])
```

---

## Dashboard Structure  

The report consists of four analytical pages:

- **Rainfall Analysis**
- **Temperature Analysis**
- **Humidity Analysis**
- **Yield Analysis**

Each page provides crop-wise, region-wise, season-wise, and year-wise breakdowns.

---

## Key Insights  

### 1. Crop Yield Analysis  

- Highest Yielding Crop: **Cotton (~51K)**
- Second Highest: **Coconut (~34K)**
- Third Highest: **Ginger (~26K)**
- Lowest Yielding Crop: **Cardamom (~7K)**

Cotton significantly outperforms other crops in overall productivity.

---

### 2. Year-wise Yield Trend  

- Peak Yield: **2010 (~28.7K)**
- Major Drop: **2015 (~16.4K)**
- Recovery observed in later years (~27.8K)

Agricultural productivity shows strong year-to-year fluctuations.

---

### 3. Regional Performance  

- Top Performing Region: **Kodagu (~28.7K)**
- Followed by: Mysuru and Madikeri
- Lowest Performing Region: **Davangere (~11.8K)**

Regional environmental conditions strongly influence yield.

---

### 4. Seasonal Performance  

- Highest Yield: **Rabi (~24.9K)**
- Moderate: Zaid (~22.0K)
- Lower: Kharif (~20.2K)

Season selection plays a major role in maximizing productivity.

---

### 5. Environmental Impact  

- Rainfall shows **moderate association** with yield  
- Temperature alone does not guarantee higher productivity  
- Humidity variation remains minimal (~55–56)

Yield depends on **multi-factor environmental interaction**, not a single variable.

---

## Project Outcome  

This project demonstrates:

- End-to-end **cloud-based data pipeline**
- SQL-driven **data transformation**
- DAX-based **analytical modeling**
- Multi-page interactive dashboard design
- Insight extraction for **strategic agricultural planning**
