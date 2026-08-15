# DSA3050A Business Intelligence & Data Visualization
## Power BI End Semester Practical Examination

**Student Name:** Lavender Achieng’ Onyango  
**Registration Number:** 671809  
**Course:** DSA3050A – Business Intelligence & Data Visualization  

---

## 1. Project Overview

This project uses **Microsoft Power BI to analyse the Global Superstore dataset and turn the available sales information into useful business insights**. The analysis moves from preparing the raw data to creating calculations, visualisations, and an interactive report.

The dataset contains information on areas such as **sales, products, customers, locations, orders, shipping, and profit**. These fields are used to examine business performance from different perspectives.

The project covers the main stages of the analysis: **cleaning and preparing the data in Power Query, organizing it into a suitable data model, creating DAX measures, developing interactive dashboards, and interpreting the results**. The final report is intended to make it easier to identify patterns in sales and profitability and support informed business decisions.

---

# 2. Dataset Selection and Understanding

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
> **Screenshot: Raw Dataset**
><img width="1895" height="967" alt="Screenshot 2026-08-15 094656" src="https://github.com/user-attachments/assets/477f8aa3-ee59-4e2c-8c06-828a5a955ffd" />

---

## 2.2 What the Dataset Represents

The Global Superstore dataset contains records of day-to-day sales transactions. It includes details about the **orders, products, customers, locations, shipping, sales, quantities, and profit**.

Each transaction provides information that can be analysed from several
perspectives, including product performance, customer segments, geographic
performance, sales trends, order activity, shipping and profitability.

Because the dataset contains both transaction details and business measures, it provides a good basis for building the Power BI report and exploring the main sales and profitability patterns.

---

## 2.3 Reason for Selecting the Dataset

The Global Superstore dataset was selected because it provides sufficient
complexity for meaningful Business Intelligence analysis.

## Main Variables in the Dataset

The dataset contains a range of variables that support different types of business analysis:

- **Sales, Profit, Quantity and Shipping Cost** – numerical fields used to measure sales performance, profitability, product volume, discounts and shipping costs.
- **Category, Sub-Category, Segment and Ship Mode** – categorical fields used to compare performance across products, customer groups and shipping methods.
- **Order Date and Ship Date** – date fields used to analyse sales trends over time and examine shipping duration.
- **Order ID, Customer ID and Product ID** – identification fields used to distinguish individual orders, customers and products.
- **Customer Name and Product Name** – fields that allow more detailed analysis at the customer and product levels.
- **Country, City, State, Region and Market** – geographic fields used to compare sales and profit across different locations.
- **Order Priority** – a field showing the priority assigned to each order.

These variables provide different ways of examining the business, including **sales, profitability, product performance, customer activity, geographic performance and shipping operations**.

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

The project focuses on turning the transactional information in the Global
Superstore dataset into a useful and interactive Power BI report. The analysis
looks at the main areas of business performance, including **sales,
profitability, products, customers, geographic regions and changes over time**.

The aim is to use the available data to identify areas where the business is
performing well, areas that may require attention, and how sales relate to
profitability.

The report therefore starts with an overall view of business performance,
followed by more detailed analysis of products and sales, and then focuses on
profitability and other factors that may help explain the results.

---

# 4. Analytical Questions

The Power BI report was developed around the following questions:

1. What are the overall sales, profit, orders and customer performance of the
   business?

2. How does sales performance change over time?

3. Which product categories and sub-categories generate the highest sales?

4. Which product categories and sub-categories generate the highest profit?

5. Which regions contribute the most to sales and profitability?

6. Which customer segments contribute the most sales?

7. Which products demonstrate strong or weak sales and profitability
   performance?

8. Which areas of the business show strong sales but relatively weak
   profitability?

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

1. Removed redundant/junk columns (记录数, Row ID)
2. Fixed Order Date and Ship Date data types (text → Date)
3. Created a Shipping Duration (Days) custom column
4. Resolved the Market vs Market2 redundancy
5. Standardized the Region field (disambiguated reused names across markets)
6. Extracted Order Month, Order Quarter and Order Year from Order Date
7. Created a conditional Sales Category column
8. Cleaned Product Name text encoding 
9. Created a DimCustomer reference table (deduplicated)

The transformation was selected to improve data quality,
consistency or analytical usefulness.

---

## Section B: Power Query — Data Cleaning & Transformation

The raw **Global Superstore** dataset (51,290 rows, 27 columns) contained no
missing values or duplicate rows, but had several structural, type, and design
problems that made it unsuitable for direct analysis. Below are the
transformations applied in Power Query that transformed it  from being raw data into an
analysis-ready data.

> **Power Query Applied Steps**
>
><img width="1917" height="1001" alt="Screenshot 2026-08-15 103044" src="https://github.com/user-attachments/assets/05ece459-cc54-4a6e-ac29-1729c9e74432" />

> 
---

### Transformation 1: Removed Redundant and Unnecessary Columns

**Problem:** The original dataset contained fields that were not useful for the
planned analysis. In particular, `记录数` (record count) contained the value
`1` for every row and did not provide additional information about the
transactions.  The dataset also contained `Row ID`, which was simply a
sequential identifier and was not required for the planned business analysis. Also
the `Discount` had 0 in all the rows therefore, it was removed because it had no meaningful
information about discounts given.

**Transformation:** The `记录数`, `Row ID` and `Discount` columns were removed from the
FactSales query using **Remove Columns** in Power Query.

**Reason:** These fields did not contribute to the sales, profitability,
product, customer, geographic or shipping analysis. Removing them reduced
unnecessary clutter and made the dataset easier to work with. It also removed
the non-English `记录数` field, resulting in a clearer and more consistent
schema.

**Result:** The three unnecessary columns were removed, leaving the fields that
were relevant to the analysis and subsequent data modelling.

**Screenshot:**

<img width="1912" height="977" alt="Screenshot 2026-08-15 102641" src="https://github.com/user-attachments/assets/cdb56343-f370-4981-b6fe-5dd4d0c9136f" />

---

### Transformation 2: Fixed Order Date and Ship Date Data Types

**Problem:** `Order Date` and `Ship Date` required the correct data type to
support date-based analysis and calculations.

**Transformation:** The data type of both `Order Date` and `Ship Date` was
changed to **Date** using Power Query.

**Reason:** Correct date formatting is necessary for analysing sales over time,
creating date-related fields and calculating the number of days between an
order and its shipment.

**Result:** Both fields were converted to Date values and were ready for
time-based analysis and shipping calculations.

**Screenshot:**
<img width="1911" height="971" alt="Screenshot 2026-08-15 102705" src="https://github.com/user-attachments/assets/0c7c314f-4983-417b-9fb4-da6ae711c26f" />

---

### Transformation 3: Created a Shipping Duration Column

**Problem:** The dataset contained separate `Order Date` and `Ship Date`
fields, but did not directly show how many days an order took to ship.

**Transformation:** A custom column was created to calculate the difference
between `Ship Date` and `Order Date`.

**Reason:** Shipping duration provides an additional measure that can be used
to examine operational performance and compare shipping times across different
shipping modes.

**Result:** A new shipping-duration field was added to the dataset and used to
support the shipping analysis in the Power BI report.

**Screenshot:**

<img width="1917" height="982" alt="Screenshot 2026-08-15 102801" src="https://github.com/user-attachments/assets/d0072817-ac9f-4964-8d88-376935fdadbf" />

---

### Transformation 4: Resolved the Market and Market2 Redundancy

**Problem:** The dataset contained both `Market` and `Market2`, which provided
overlapping geographic information. The two fields did not always classify
locations in the same way.

**Transformation:** The unnecessary `Market2` field was removed and the
`Market` values were standardised using **Replace Values**.

**Reason:** Keeping two conflicting geographic fields could result in
inconsistent groupings and confusing filtering in the report.

**Result:** A single, consistent `Market` field was retained for geographic
analysis.

**Screenshot:**
<img width="1886" height="952" alt="image" src="https://github.com/user-attachments/assets/2de6395c-e579-4c01-a355-773ead4eb82a" />

---

### Transformation 5: Standardised the Region Field

**Problem:** Some `Region` names were repeated across different markets. For
example, the same regional name could occur in more than one market, making it
difficult to distinguish between them when analysing regional performance.

**Transformation:** A custom column was created by combining the relevant
market and region information. The resulting values were then used to provide
clearer regional labels.

**Reason:** This prevents different geographic areas with the same region name
from being grouped together incorrectly.

**Result:** Region values were made more distinct and suitable for use in
visuals, slicers and geographic analysis.

**Screenshot:**

<img width="1907" height="996" alt="Screenshot 2026-08-15 160510" src="https://github.com/user-attachments/assets/1578e075-9a3e-48e8-bdfa-220cb1d55c65" />

---

### Transformation 6: Extracted Order Month and Order Quarter

**Problem:** The dataset contained year information but required additional
date details for more detailed time-based analysis.

**Transformation:** **Month Name** and **Quarter** were extracted from
`Order Date`. The quarter values were formatted as Q1, Q2, Q3 and Q4.

**Reason:** Including month and quarter information makes it possible to
examine sales patterns at different points during the year.

**Result:** Additional date fields were created to support time-based analysis
and the Power BI visuals.

**Screenshot:**

<img width="1917" height="998" alt="Screenshot 2026-08-15 102854" src="https://github.com/user-attachments/assets/736148cb-54e8-4dc8-8821-d7308801658e" />

---

### Transformation 7: Created a Conditional Column

**Problem:** Some sales information in the dataset was available as raw values but
could be made easier to interpret by grouping it into meaningful categories.

**Transformation:** A conditional column was created in Power Query using
specified conditions to classify the records into meaningful groups.

**Reason:** Grouping values into categories makes the information easier to
compare and use in Power BI visuals.

**Result:** A new sales categorical field was created that could be used for further
analysis and filtering.

**Screenshot:**

<img width="1917" height="957" alt="Screenshot 2026-08-15 103026" src="https://github.com/user-attachments/assets/385968d7-491c-4d1c-a14e-26758d1f81f2" />

---

### Transformation 8: Cleaned Product Name Text

**Problem:** Some `Product Name` values contained unnecessary spaces,
non-printable characters or inconsistent text formatting.

**Transformation:** The Product Name field was processed using **Trim** and
**Clean** operations. 

**Reason:** Consistent product names are important when grouping products,
searching for products or displaying them in tables and visuals.

**Result:** The Product Name values were cleaned and standardised, improving
the consistency of product-level analysis.

**Screenshot:**

<img width="1917" height="990" alt="Screenshot 2026-08-15 103006" src="https://github.com/user-attachments/assets/535357b1-a235-4d9d-a170-3a91774d3c64" />

---

### Transformation 9: Created a DimCustomer Reference Table

**Problem:** Customer information such as `Customer ID`, `Customer Name` and
`Segment` was repeated across many transaction records in the original flat
dataset.

**Transformation:** A reference query was created from the cleaned FactSales
query. The relevant customer fields were retained and duplicate customer
records were removed to create the `DimCustomer` table.

**Reason:** Separating customer information from transaction data provides a
cleaner structure for the data model and avoids unnecessary repetition.

**Result:** A separate `DimCustomer` table was created with unique customer
information. The table was then available to form a relationship with the
FactSales table using `Customer ID`.

**Screenshot:**

<img width="1917" height="937" alt="Screenshot 2026-08-15 161131" src="https://github.com/user-attachments/assets/8fd30669-2522-4ea0-a453-f07b14931c4c" />

---

### Summary of the Power Query Transformations

The transformations prepared the Global Superstore dataset for the next
stages of the project. Unnecessary fields were removed, data types were
corrected, text and geographic information were standardised, additional date
and shipping information was created, and the customer information was
separated into a dimension table.

The resulting data was therefore more suitable for **data modelling, DAX
calculations, interactive visualisation and business analysis**.

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

The data model connects the `FactSales` table with the relevant dimension
tables through defined relationships. One-to-many relationships were used
where appropriate, with the dimension tables acting as the main source of
filtering for the transaction data.

The relationships were structured to keep the model simple and avoid
unnecessary many-to-many relationships or ambiguous filtering paths.
Single-direction filtering was also used where appropriate so that filters
flow clearly from the dimension tables to `FactSales`.

---

## 6.7 Modelling Challenges

A key challenge was creating relationships between `FactSales` and the
dimension tables without introducing ambiguous filtering or unnecessary
many-to-many relationships.

Another consideration was connecting `DimDate` correctly to `FactSales` so
that time-based analysis, such as sales trends and would work correctly.

The final model uses `FactSales` as the central transaction table, with
descriptive information separated into dimension tables. This provides a clear
structure for filtering, calculations and analysis.

> **Screenshot: Completed Data Model**
><img width="1527" height="796" alt="Screenshot 2026-08-15 095556" src="https://github.com/user-attachments/assets/bec65e72-ab80-411d-95f1-4565094d88d3" />

> 
---

# 7. DAX Measures and Business Calculations

12 meaningful DAX measures was developed to transform the data
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

---

## 7.1 Six Most Important DAX Measures

### 1. Total Sales

```dax
Total Sales = SUM(FactSales[Sales])
```

**What it calculates:** Calculates the total sales generated from all transactions.

**Why it is useful:** Total Sales is a key performance indicator used to evaluate overall business sales performance and compare sales across categories, regions, products and time periods.

**Main DAX function used:** `SUM()`

**Filter context:** The measure responds to the active filter context. For example, selecting a specific year, region or category changes the total sales displayed.

**Dashboard use:** Used as a KPI card and in sales analysis visualizations.

---

### 2. Total Profit

```dax
Total Profit = SUM(FactSales[Profit])
```

**What it calculates:** Calculates the total profit generated from all transactions.

**Why it is useful:** Total Profit provides an overall measure of business profitability and allows performance to be compared across categories, regions and products.

**Main DAX function used:** `SUM()`

**Filter context:** The measure changes according to the active filters applied to the report.

**Dashboard use:** Used as a KPI card and in profitability analysis visualizations.

---

### 3. Profit Margin %

```dax
Profit Margin % =
DIVIDE(
    [Total Profit],
    [Total Sales],
    0
)
```

**What it calculates:** Calculates profit as a percentage of total sales.

**Why it is useful:** Profit Margin % measures profitability relative to sales and allows meaningful comparison between different categories, regions and products.

**Main DAX function used:** `DIVIDE()`

**Filter context:** The measure responds to the current filter context. For example, selecting a particular category calculates the profit margin for that category.

**Dashboard use:** Used as a KPI card and in profitability analysis.

---

### 4. Total Orders

```dax
Total Orders = DISTINCTCOUNT(FactSales[Order ID])
```

**What it calculates:** Counts the number of unique orders in the dataset.

**Why it is useful:** `DISTINCTCOUNT()` ensures that an order containing several products or transaction rows is counted as one order rather than being counted multiple times.

**Main DAX function used:** `DISTINCTCOUNT()`

**Filter context:** The measure changes when filters such as Year, Region, Category or Customer Segment are applied.

**Dashboard use:** Used as a KPI card on the Executive Overview page.

---

### 5. YoY Sales Growth %

*Only use this measure if you already created `[Previous Year Sales]`.*

```dax
YoY Sales Growth % =
DIVIDE(
    [Total Sales] - [Previous Year Sales],
    [Previous Year Sales],
    0
)
```

**What it calculates:** Calculates the percentage change in sales compared with the previous year.

**Why it is useful:** This measure helps determine whether sales performance has increased or decreased over time.

**Main DAX functions used:** `DIVIDE()` and the supporting `[Previous Year Sales]` measure.

**Filter context:** The result changes according to the selected time period and other active report filters.

**Dashboard use:** Used as a KPI to communicate year-over-year sales performance.

---

### 6. Category Sales Rank

```dax
Category Sales Rank =
RANKX(
    ALL(FactSales[Category]),
    [Total Sales],
    ,
    DESC,
    DENSE
)
```

**What it calculates:** Ranks product categories according to their total sales, with the highest-selling category receiving rank 1.

**Why it is useful:** The measure allows categories to be compared and identifies the strongest and weakest categories in terms of sales.

**Main DAX functions used:** `RANKX()` and `ALL()`.

**Filter context:** `ALL()` removes the category filter when calculating the ranking, allowing each category to be compared against all categories.

**Dashboard use:** Used in category-level sales analysis to identify the relative performance of product categories.

# 8. Dashboard Design and Analysis

The Power BI report consists of three interactive dashboard pages designed to
provide a progression from overall business performance to detailed sales and
product analysis and finally to profitability and diagnostic analysis.

The dashboards use KPI cards, charts, tables, slicers and interactive
filtering to allow users to explore the business performance from different
perspectives.

---

## 8.1 Executive Overview

The Executive Overview provides a high-level summary of the overall business
performance.

The dashboard displays the following key performance indicators:

- **Total Sales:** 12.64M
- **Total Profit:** 1.47M
- **Total Orders:** 25K
- **Total Customers:** 5K
- **Total Profit Margin:** 11.61%
- **YoY Sales Growth:** 51.54%

The dashboard also presents sales trends over time, sales by region and total
sales by category. Year, Region and Category slicers allow users to filter
the dashboard and examine specific parts of the business.

The sales trend shows an increase in total sales from approximately **2.3M in
2011** to **4.3M in 2014**. At category level, **Technology** records the
highest sales at approximately **4.7M**, followed by Furniture at **4.1M** and
Office Supplies at **3.8M**.

The Executive Overview therefore provides management with a concise view of
overall sales, profitability, customer and order performance.

**Screenshot:**

<img width="1436" height="796" alt="05_dashboard_overview" src="https://github.com/user-attachments/assets/b1421a54-ac21-41ae-8cf2-05f9778c90ae" />

---

## 8.2 Sales and Product Analysis

The Sales and Product Analysis dashboard provides a more detailed examination
of product, category, sub-category and customer segment performance.

The Product Performance table displays:

- Product Name
- Category
- Sub-Category
- Total Sales
- Total Profit
- Profit Margin %

The dashboard also contains Total Profit by Sub-Category, Total Sales by
Sub-Category and Total Sales by Customer Segment visualizations.

The sub-category analysis shows **Phones** as the highest-selling sub-category
at approximately **1.71M**, followed by **Copiers** at approximately **1.51M**
and **Chairs** at approximately **1.50M**.

The customer segment analysis shows that the **Consumer segment** contributes
the largest share of sales at approximately **6.51M (51.48%)**, followed by
Corporate at approximately **3.82M (30.25%)** and Home Office at approximately
**2.31M (18.27%)**.

The dashboard also provides Category and Region filters for more focused
analysis.

**Screenshot:**

<img width="1444" height="798" alt="06_dashboard_analysis" src="https://github.com/user-attachments/assets/4cc5d641-1fa7-4790-8cb1-8a906debf8cf" />

---

## 8.3 Profitability and Diagnostic Insights

The Profitability and Diagnostic Insights dashboard focuses on profitability
and operational performance.

The dashboard displays:

- **Average Profit per Order:** $58.6162
- **Overall Profit Margin:** 11.61%
- **Current Profit Status:** Profitable

The Sales versus Profit by Category visualization shows the relationship
between sales and profit across Furniture, Office Supplies and Technology.

Technology records the highest profit at approximately **0.66M**, followed by
Office Supplies at approximately **0.52M** and Furniture at approximately
**0.29M**.

The Profit by Region visualization shows **EU - Central** as the highest
displayed region at approximately **0.22M**, followed by **APAC - North Asia**
at approximately **0.17M**.

The Average Shipping Time by Ship Mode visualization shows that **Standard
Class** has the highest average shipping time at approximately **5.00 days**,
followed by **Second Class** at **3.23 days**, **First Class** at **2.18 days**
and **Same Day** at approximately **0.04 days**.

This page provides a deeper view of profitability and shipping performance,
helping identify differences between product categories, regions and
shipping modes.

**Screenshot:**

<img width="1381" height="801" alt="07_dashboard_insights" src="https://github.com/user-attachments/assets/a3db4faf-826c-47ee-a9ad-6891334c2a9e" />

---

# 9. Power BI Interactivity

The report incorporates interactive features that allow users to explore the
data dynamically.

### Slicers

Year, Region and Category slicers are provided across the dashboards. Users
can select specific values to filter the displayed KPIs and visualizations.

### Cross-Filtering

The visualizations interact with one another. Selecting a category, region or
other relevant data point allows the user to examine the corresponding
changes in other visuals.

### Drill-Down

The product analysis provides information at different levels of product
detail, including Category, Sub-Category and Product, allowing users to
investigate product performance at a more detailed level.

**Screenshot:**
<img width="1335" height="751" alt="Screenshot 2026-08-15 175319" src="https://github.com/user-attachments/assets/026fac12-b856-4c0a-886d-205ca7c98bdb" />


### Page Navigation

Navigation between the dashboard pages allows users to move from the
Executive Overview to Sales and Product Analysis and then to Profitability and
Diagnostic Insights.

**Screenshot:**

<img width="1502" height="852" alt="Screenshot 2026-08-15 172442" src="https://github.com/user-attachments/assets/465d1d35-c668-4bd1-87ba-1b08b998ec71" />

### Bookmarks

A Reset Filters bookmark was implemented to return the dashboard to its
default view after filters have been applied.

**Screenshot:**

<img width="1447" height="852" alt="Screenshot 2026-08-15 172442" src="https://github.com/user-attachments/assets/a8f28022-d290-437b-ba7f-972db2a730e3" />


---

# 10. Key Dashboard Findings

The dashboards provide the following important findings:

1. **Overall Performance:** The business generated total sales of **12.64M**
   and total profit of **1.47M**, with an overall profit margin of **11.61%**.

2. **Sales Growth:** Total sales increased from approximately **2.3M in 2011**
   to **4.3M in 2014**, indicating strong growth over the period displayed.

3. **Category Performance:** **Technology** generated the highest total sales
   at approximately **4.7M** and also recorded the highest profit at
   approximately **0.66M**.

4. **Customer Segment:** The **Consumer segment** generated the largest sales
   contribution at approximately **6.51M (51.48%)**.

5. **Regional Profitability:** **EU - Central** recorded the highest displayed
   regional profit at approximately **0.22M**.

6. **Shipping Performance:** **Standard Class** had the highest average
   shipping time at approximately **5 days**, while Same Day shipping had the
   lowest average at approximately **0.04 days**.

These findings demonstrate how the dashboard can be used to assess overall
performance, identify high-performing categories and segments, compare
regional profitability and evaluate shipping performance.
