# E-commerce-Sales-Analysis
This is an E-commerce Sales Analysis to uncover key trends shaping Sales Performance using Power bi.

![image](Power_bi.png)

---

## Introduction 

---
## Problem Statement 

---
## Data Transformation and Cleaning 

---
## Data Normalization 

---
## Data Modelling 

![image](Data_Modelling.JPG)

---

## Analysis and Calculations Using DAX

This analysis was done using DAX to quantify the various metic which where grouped into;
- **Base Measure** : Total Sales,Total Quantity etc
- **Previous Year (PY) Measure** :PY Sales,PY Qty etc
-  **Year Over Year (YOY) Measure** &
- **Color Measures which is the conditional colour Indicator**.

### Base Measure

- **Total Sales**

Total Sales = SUM(fact_table[Sales])

- **Total Quantity**

Total Qty = SUM(fact_table[quantity])

- **Average Unit Price**

Avg Unit Price = AVERAGE(fact_table[unit_price])

- **Customers**

Customers = DISTINCTCOUNT(fact_table[Customer_key])

### Previous Year (PY) Measure

- **Previous Year Sales**

PY Sales = 
CALCULATE(
    [Total Sales],
    SAMEPERIODLASTYEAR(time_dim[Date]),
    REMOVEFILTERS()
)

- **Previous Year Quantity**

PY Qty = 
CALCULATE(
    [Total Qty],
    SAMEPERIODLASTYEAR(time_dim[Date]),
    REMOVEFILTERS()
)

- **Previous Year Unit Price**

PY Price = 
CALCULATE(
    [Avg Unit Price],
    SAMEPERIODLASTYEAR(time_dim[Date]),
    REMOVEFILTERS()
)

- **Previous Year Customers**

PY Customers = 
CALCULATE(
    [Customers],
    SAMEPERIODLASTYEAR(time_dim[Date]),
    REMOVEFILTERS()
)

### Year Over Year (YOY) Measures

- **YoY Sales %**

% YOY Sales =

VAR a = DIVIDE([Total Sales],[PY Sales]) - 1
VAR label = FORMAT(a,"#0.0%")
RETURN label & IF(a > 0, "▲","▼")

- **YoY Quantity %**

% YOY Qty =

VAR a = DIVIDE([Total Qty],[PY Qty]) - 1
VAR label = FORMAT(a,"#0.0%")
RETURN label & IF(a > 0, "▲","▼")

- **YoY Price %**

% YOY Price =

VAR a = DIVIDE([Avg Unit Price],[PY Price]) - 1
VAR label = FORMAT(a,"#0.0%")
RETURN label & IF(a > 0, "▲","▼")

- **YoY Customers %**

% YOY Customers =

VAR a = DIVIDE([Customers],[PY Customers]) - 1
VAR label = FORMAT(a,"#0.0%")
RETURN label & IF(a > 0, "▲","▼")

### Color Measures 

- **Sales Color Indicator**

Sales Color = IF([Total Sales] > [PY Sales], "#85BD5F", "#A83F22")

- **Quantity Color Indicator**

Qty Color = IF([Total Qty] > [PY Qty], "#85BD5F", "#A83F22")

- **Price Color Indicator**

Price Color = IF([Avg Unit Price] > [PY Price], "#85BD5F", "#A83F22")

- **Customer Color Indicator**

Customer Color = IF([Customers] > [PY Customers], "#85BD5F", "#A83F22")


---

## Data Visualisation (Dashboard)

![image](Dashboard.JPG)

---

## Insights 

--- 
## Conclusion 

--- 
## Recommendation 

---
## About me 

- I transform complex data into , actionable insights.
Using analytics, machincleare learning, and visualization, I help you understand trends, improve efficiency, and plan for the future.

Connect with me @https://www.linkedin.com/in/adetokunbo-olasupo-70aa042a1

