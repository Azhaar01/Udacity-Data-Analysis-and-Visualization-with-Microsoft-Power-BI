# **Create a Data Model for Seven Sages Tea Company**

Project 1 of Udacity's [Data Analysis and Visualization with Microsoft Power BI Nanodegree Program](https://www.udacity.com/course/data-analysis-and-visualization-with-power-BI-nanodegree--nd331)
in **Preparing and Modeling Data** course.

## Project Description:
The project is to create a Power BI data model and report for Seven Sages Tea Company (SSTC). This data model will allow a company's CFO to quickly review and analyze which tea drinks are selling well and which ones are generating the highest profitability so they can make smart decisions about which products to prioritize as the company continues to grow.
The project demonstrates an understanding of basic data modeling principles, including the ability to clean, organize, and structure data in Power Query, create a date table, create a data model with appropriate relationships and filters, and create a simple report using common visualizations and DAX metrics.

Below is a quick demonestration about project steps:

### Get Data:
used files are `CFO Metrics Tracker.xlsx`, `Customer List (as of FY2021).txt`,
 `SSTC Product Offerings.pdf`, `USD-CAD Exchange Rates.csv`, 
 `Monthly Sales Logs/` downloaded from Udacity and can be found on `Source Files/` folder on this repo.

### ETL with Power Query:
We used Power Query to make data cleaning/pre-processing on our datasets, that included:
  - Merging 12 monthly sales files into `Sales` query for better analysis.
  - Merging `CFO Metrics Tracker.xlsx` and `SSTC Product Offerings.pdf` to `Product list` query to include all product relevalt attributes.
  - Promoted first rows as headers.
  - Removed NULL values in all datasets.
  - Renamed queries and columns with descriptive names.
  - Changed columns' data types to suitable ones.
  - Built dynamic date table that we'll dive into in the next section.    

### Creating Date Table:
A date table has been created using Power Query that is set to dynamically update based on the fact table’s start and end data.
The date table includes standard fields:

  - Date
  - Calendar month name and number
  - Calendar year
  - Quarter 
  - Fiscal period
  - Fiscal year
  - Fiscal quarter -Quarter - FY (e.g., Q1 - FY2021)

> Note: Seven Sages' Fiscal year begins on October 1st and runs until September 30th. A transaction on Sept 20th 2020 would fall in FY 2020, but a transaction on October 20th would land in FY 2021


### Create Data Model (build relationships between tables):
We ended up with one fact table `Sales` and four diminsion tables pointing towards it with an active one to many relationship.
a snapshot of the data model is provided below and can be found on `SSTC-Data-Model.png` on this repo.

![SSTC Data Model](https://github.com/Azhaar01/Udacity-Data-Analysis-and-Visualization-with-Microsoft-Power-BI/blob/main/01-Create%20a%20Data%20Model%20for%20Seven%20Sages%20Tea%20Company/SSTC-Data-Model.png)

### Writing DAX Measures:
To satisfy the CFO's requirements, we will need to write six measures—to calculate Sales, 
Cost of Sales and Gross Profit Margin in two different currencies.
The following measures have been created using DAX, are present on the data model, and are clearly labeled:

  - Sales USD ($)
  - Cost of Sales USD ($)
  - Gross Profit Margin (or GPM) in USD (%)
  - Sales CAD ($)
  - Unit Sales by Product (%)
  - Gross profit by Product (%)

### Build a Report
To satisfy the CFO's requirements, our basic version of report will have two tabs, one summarizing sales by customer and customer type across quarters and would be labeled `Sales and GPM`. 
The second will simply summarize the percentages of gross profit and unit sales by product and would be labeled `Gross Profit and Unit Sales`.
Both tabs has a very brief executive summary at the bottom.
Full PDF report can be found on `SSTC-Report` file provided on this repo.

![SSTC Report Tab 1](https://github.com/Azhaar01/Udacity-Data-Analysis-and-Visualization-with-Microsoft-Power-BI/blob/main/01-Create%20a%20Data%20Model%20for%20Seven%20Sages%20Tea%20Company/SSTC-Report-Tab1.png)


![SSTC Report Tab 2](https://github.com/Azhaar01/Udacity-Data-Analysis-and-Visualization-with-Microsoft-Power-BI/blob/main/01-Create%20a%20Data%20Model%20for%20Seven%20Sages%20Tea%20Company/SSTC-Report-Tab2.png)
