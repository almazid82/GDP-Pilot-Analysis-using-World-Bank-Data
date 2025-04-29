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


____


## output:

Country Name | Year | GDP (Current US$)     |
|--------------|------|------------------------|
| Bangladesh   | 2020 | 302571000000           |
| Bangladesh   | 2021 | 416264000000           |
| Bangladesh   | 2022 | 460000000000           |
| India        | 2020 | 2668670000000          |
| India        | 2021 | 3176290000000          |
| India        | 2022 | 3393000000000          |
| USA          | 2020 | 20937000000000         |
| USA          | 2021 | 23151000000000         |
| USA          | 2022 | 25460000000000         |


---
