# DSA3050A Business Intelligence & Data Visualization
## Power BI End Semester Practical Examination

**Student Name:** Lavender Achieng’ Onyango  
**Registration Number:** 671809  
**Course:** DSA3050A – Business Intelligence & Data Visualization  

---
## Dataset Source

Source: **Global Superstore Dataset**

The dataset was obtained from Kaggle and contains transactional sales data
from a global superstore.

Source: **Kaggle – Global Superstore Dataset**  
https://www.kaggle.com/datasets/fatihilhan/global-superstore-dataset

## Dataset Summary

- **Number of Rows:** 51,290
- **Number of Columns:** 24
- **Time Period:** 2011–2015
- **Dataset Type:** Transactional retail sales data
---

## 1. Project Overview

This project presents a complete Business Intelligence solution developed using
Microsoft Power BI. The objective is to transform raw transactional data into
an interactive analytical solution that supports business performance
monitoring, detailed analysis, and data-driven decision-making.

The project follows the complete Business Intelligence development process:

**Dataset → Power Query → Data Model → DAX → Dashboard → Insights**

The analysis uses the Global Superstore dataset, which contains transactional
information relating to sales, products, customers, locations, orders,
shipping, and profitability.

The solution demonstrates data acquisition and understanding, data cleaning and
transformation using Power Query, dimensional data modelling, DAX-based
business calculations, interactive dashboard development, and interpretation
of analytical results.

---

# 2. Dataset Selection and Understanding

## 2.1 Dataset Source

The dataset used for this project is the **Global Superstore dataset**.

**Source:**https://www.kaggle.com/code/osmanahmedosman/global-superstore/input

The dataset was obtained from a publicly available source and contains
transaction-level information suitable for Business Intelligence analysis.

> **Screenshot: Raw Dataset**
><img width="1895" height="967" alt="Screenshot 2026-08-15 094656" src="https://github.com/user-attachments/assets/477f8aa3-ee59-4e2c-8c06-828a5a955ffd" />

---

## 2.2 What the Dataset Represents

The Global Superstore dataset represents transactional business data covering
sales activities across products, customers, locations, order dates, shipping
methods, quantities, sales and profit.

Each transaction provides information that can be analysed from several
perspectives, including product performance, customer segments, geographic
performance, sales trends, order activity, shipping and profitability.

The transactional structure of the dataset makes it suitable for developing
an analytical model and interactive Power BI dashboards.

---

## 2.3 Reason for Selecting the Dataset

The Global Superstore dataset was selected because it provides sufficient
complexity for meaningful Business Intelligence analysis.

The dataset contains:

- Numerical variables for quantitative analysis
- Categorical variables for segmentation
- Date fields for time-based analysis
- Sales and profit measures for KPI development
- Product and sub-category information
- Customer information
- Geographic information
- Shipping information

These characteristics allow the development of multiple analytical
perspectives rather than limiting the analysis to a single business measure.

---

## 2.4 Main Variables

The major variables used in the analysis include:

| Variable | Description |
|---|---|
| Order ID | Identifies an individual customer order |
| Order Date | Date on which the order was placed |
| Ship Date | Date on which the order was shipped |
| Customer ID | Identifies the customer |
| Customer Name | Customer name |
| Segment | Customer segment |
| Category | Main product category |
| Sub-Category | Product sub-category |
| Product Name | Individual product |
| Sales | Sales value generated |
| Profit | Profit generated |
| Quantity | Number of units sold |
| Region | Geographic region |
| Country | Country of the transaction |
| Ship Mode | Shipping method |

---

# 3. Business / Analytical Problem

The main analytical problem investigated in this project is:

**How can transactional sales data be transformed into an interactive
Business Intelligence solution that enables management to evaluate sales
performance, profitability, product performance, customer activity,
geographic performance and changes over time?**

The analysis focuses on identifying areas of strong performance, areas
requiring attention, and relationships between sales and profitability.

The Power BI solution is therefore designed to move from an overall view of
business performance to detailed product analysis and finally to deeper
profitability and diagnostic analysis.

---

# 4. Analytical Questions

The Power BI solution was developed to answer the following analytical
questions:

1. What are the overall sales, profit, orders and customer performance of the
   business?

2. How does sales performance change over time?

3. Which product categories and sub-categories generate the highest sales?

4. Which product categories and sub-categories generate the highest profit?

5. Which regions contribute the most to sales and profitability?

6. Which customer segments contribute the most sales?

7. Which products demonstrate strong or weak sales and profitability
   performance?

8. How does profitability compare across different business segments and
   geographic regions?

9. How does shipping time vary across different shipping modes?

10. How does sales performance compare with profitability?

These questions are important because they provide the basis for the DAX calculations, visualizations and
dashboard storytelling developed in this project.

---

# 5. Power Query – Data Cleaning and Transformation

Power Query was used to prepare the raw dataset for analysis before it was
loaded into the Power BI data model.

The transformations were selected based on the characteristics and analytical
requirements of the dataset.

The major transformations performed included:

1. Reviewing and removing unnecessary fields where appropriate.
2. Correcting and standardizing data types.
3. Cleaning text fields.
4. Handling missing or null values where applicable.
5. Removing duplicate records where appropriate.
6. Standardizing categorical values.
7. Extracting useful information from date fields.
8. Creating a Shipping Days custom column.
9. Renaming fields to improve clarity and consistency.
10. Preparing the cleaned data for dimensional modelling.

The transformations were not performed simply for the purpose of increasing
the number of steps. Each transformation was selected to improve data quality,
consistency or analytical usefulness.

---

## 5.1 Power Query Transformation Documentation

### Transformation 1 – Data Type Correction

**Problem:** Some fields required appropriate data types before analysis.

**Transformation:** Data types were reviewed and corrected in Power Query.

**Reason:** Correct data types are necessary for accurate calculations,
filtering and time-based analysis.

**Result:** The relevant fields were assigned appropriate data types.

---

### Transformation 2 – Removing Unnecessary Columns

**Problem:** Some fields were not required for the intended analysis.

**Transformation:** Unnecessary columns were removed from the working dataset.

**Reason:** Removing irrelevant fields simplifies the model and focuses the
analysis on useful information.

**Result:** The dataset was reduced to relevant analytical fields.

---

### Transformation 3 – Cleaning Text Fields

**Problem:** Text fields may contain inconsistent formatting or unnecessary
spaces.

**Transformation:** Text-cleaning operations were applied where required.

**Reason:** Consistent text values prevent the same category from being treated
as different categories.

**Result:** Categorical fields became more consistent for grouping and
filtering.

---

### Transformation 4 – Handling Missing Values

**Problem:** Missing or null values can affect calculations and visual
groupings.

**Transformation:** Missing values were reviewed and handled where
appropriate.

**Reason:** This improves the reliability of the resulting analysis.

**Result:** Relevant fields were prepared for analysis with missing-value
issues addressed appropriately.

---

### Transformation 5 – Removing Duplicates

**Problem:** Duplicate records can result in double-counting.

**Transformation:** Duplicate records were reviewed and removed where
appropriate.

**Reason:** This helps preserve the accuracy of transaction-level analysis.

**Result:** The dataset contained the appropriate records for analysis.

---

### Transformation 6 – Standardizing Categories

**Problem:** Inconsistent categorical values can create separate groups for
values that represent the same category.

**Transformation:** Relevant categorical values were standardized.

**Reason:** Standardization ensures consistent grouping in Power BI visuals.

**Result:** Categories were represented consistently.

---

### Transformation 7 – Extracting Date Information

**Problem:** Detailed date fields are required for time-based analysis.

**Transformation:** Relevant date components were extracted from the date
fields.

**Reason:** Year and other date attributes support trend analysis and
time-based filtering.

**Result:** The dataset was prepared for time-based analysis and the creation
of a dedicated date dimension.

---

### Transformation 8 – Creating Shipping Days

**Problem:** The dataset contains both Order Date and Ship Date, but does not
directly provide the number of days required to ship an order.

**Transformation:** A custom column named `Shipping Days` was created using the
difference between Ship Date and Order Date.

**Reason:** Shipping duration provides an additional operational measure that
can be analysed by shipping mode and other dimensions.

**Result:** The model contains a derived Shipping Days field that can be used
to calculate average shipping time.

---

### Transformation 9 – Renaming Fields

**Problem:** Some field names were not sufficiently clear or consistent for
analysis.

**Transformation:** Relevant fields were renamed appropriately.

**Reason:** Clear field names improve model readability and reduce ambiguity
when creating DAX calculations and visualizations.

**Result:** The analytical model contains clearer and more consistent field
names.

---

> **Screenshot: Power Query Transformations**
>
> Insert screenshot here:
>
> `screenshots/02_power_query.png`

---

# 6. Data Modelling

The cleaned transactional dataset was transformed into an analytical data
model designed to support efficient filtering, aggregation and analysis.

The central transactional table is **FactSales**.

The model uses dimension tables to provide descriptive attributes that filter
and analyse the transactional records.

The principal tables include:

- FactSales
- DimDate
- DimCustomer
- DimProduct
- DimLocation

The actual dimensions used were determined by the structure of the dataset and
the analytical requirements of the project.

---

## 6.1 FactSales

`FactSales` is the central fact table because it contains the transactional
records and quantitative measures required for analysis.

The table contains fields such as:

- Order ID
- Customer ID
- Product information
- Location information
- Order Date
- Ship Date
- Sales
- Profit
- Quantity
- Shipping information

The fact table therefore provides the numerical business activity that is
aggregated by the dimension tables.

---

## 6.2 DimDate

`DimDate` was created to support time-based analysis.

It provides date attributes that can be used to analyse sales and other
measures across time.

The date dimension also supports the time-intelligence calculations used in
the DAX section.

---

## 6.3 DimCustomer

`DimCustomer` provides descriptive customer attributes that allow the
transactional data to be analysed from a customer perspective.

This dimension supports analysis by customer, customer segment and related
customer attributes.

---

## 6.4 DimProduct

`DimProduct` provides product-related descriptive information such as
category, sub-category and product name.

It supports detailed product performance analysis.

---

## 6.5 DimLocation

`DimLocation` provides geographic information that supports analysis of sales
and profitability across geographic areas.

---

## 6.6 Relationships

The model uses relationships between the dimension tables and `FactSales`.

Where appropriate, one-to-many relationships were used, with the dimension
tables providing filtering context for the transactional fact table.

The relationships were designed to avoid unnecessary many-to-many
relationships and ambiguous filter paths.

Single-direction filtering was used where appropriate to maintain a clear
filter flow from dimensions to the fact table.

---

## 6.7 Modelling Challenges

One of the main modelling considerations was ensuring that descriptive
dimension tables could filter the transactional fact table without creating
ambiguous relationships.

The Date table also required appropriate integration with the transaction
dates to support time-based analysis.

The model was therefore structured to separate transactional information from
descriptive attributes and to provide a clear analytical structure.

> **Screenshot: Completed Data Model**
>
> Insert screenshot here:
>
> `screenshots/03_model.png`

---

# 7. DAX Measures and Business Calculations

A minimum of 12 meaningful DAX measures was developed to transform the data
model into an analytical solution.

The measures include core KPIs, calculated business measures and advanced
calculations involving filter context, ranking and time intelligence.

The measures created were:

| No. | DAX Measure |
|---:|---|
| 1 | Total Sales |
| 2 | Total Profit |
| 3 | Total Quantity |
| 4 | Total Orders |
| 5 | Total Customers |
| 6 | Average Sales per Order |
| 7 | Profit Margin % |
| 8 | Average Profit per Order |
| 9 | Previous Year Sales |
| 10 | YoY Sales Growth % |
| 11 | Category Sales Rank |
| 12 | Profit Status |

The measures use functions including `SUM()`, `DIVIDE()`,
`DISTINCTCOUNT()`, `CALCULATE()`, `SAMEPERIODLASTYEAR()`, `RANKX()` and
`IF()`.

---

## 7.1 Six Most Important DAX Measures

### 1. Total Sales

```DAX
Total Sales =
SUM(FactSales[Sales])
