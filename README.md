# GDP-Pilot-Analysis-using-World-Bank-Data
This is a pilot project where we analyze GDP data for selected countries using **SQL**, **Python**, and **Tableau**. The goal is to understand GDP trends, compare between countries, and build visualizations for presentation.

---

## 1. Dataset Description

**Source:** [World Bank Open Data](https://data.worldbank.org/indicator/NY.GDP.MKTP.CD)  
**Indicator:** GDP (current US$)  
**Format:** CSV  
**Countries:** Bangladesh, India, China, USA  
**Time Range:** 2000 - 2022

Dataset path: `data/world_gdp.csv`

---

## 2. Step-by-Step Workflow

### Step 1: SQL for Data Filtering

We use SQL to filter GDP data by country and time range.

**Sample SQL Query:**
```sql
SELECT country_name, year, gdp
FROM world_gdp
WHERE country_name IN ('Bangladesh', 'India', 'USA')
AND year BETWEEN 2000 AND 2022;
