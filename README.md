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

 **output**

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
### SQL Output Explanation

The table above displays the GDP (in current US dollars) for Bangladesh, India, and the USA from 2020 to 2022. This data was extracted using a SQL query that filters the dataset based on:

- Selected Countries: Bangladesh, India, USA
- Selected Years: 2020, 2021, and 2022

#### Key Insights:
- **Bangladesh** shows a consistent increase in GDP from $302.6B in 2020 to $460B in 2022.
- **India** also demonstrates strong growth, reaching over $3.39 trillion in 2022.
- **USA** remains the largest economy, crossing $25 trillion GDP in 2022.

This filtered dataset will be used in the next steps for Python-based visualization and Tableau dashboard creation.


---
