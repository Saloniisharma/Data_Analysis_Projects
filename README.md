# Company Layoffs Data Cleaning Portfolio Project


## Problem Statement

In recent years, there has been a significant increase in layoffs across various industries and companies globally, driven by economic downturns, shifts in market demands, and the evolving nature of industries such as tech, finance, and crypto. The company layoff data collected from multiple sources is often inconsistent, with duplicate records, incomplete information, and unstandardized fields, making it challenging to derive actionable insights.

The goal of this project is to clean, standardize, and analyze the layoff data to understand key trends and insights. This includes identifying patterns in layoffs by industry, company, and country, as well as evaluating the impact of funding stages and time (monthly and yearly) on layoff events.


### Steps followed 

- Step 1 : Load data into MySql Workbench, dataset is a csv file.
- Step 2 : Table Duplication and Row Deduplication
 
   A staging table layoffs_staging_2 is created to safely manipulate the data. A row number is assigned using the ROW_NUMBER() window function to identify and delete duplicate entries, retaining only the unique rows.
- Step 3 : Data Standardization
  
    1. Company and Industry: Trimming extra spaces from the company and industry fields, and standardizing industry values (e.g., categorizing all 'Crypto' industry values under a single term).
    2. Country: Country values are cleaned by trimming unnecessary trailing periods (e.g., standardizing "United States." to "United States").
- Step 4 : Data Type Conversion

  The date column is converted from text to a DATE data type for accurate date-based queries using STR_TO_DATE() and ALTER TABLE.
- Step 5 : Exploratory Analysis

  1. Aggregations: Several queries provide insights into the data, such as:
  - Maximum and minimum layoffs.
   
   - Layoffs by company, industry, and country.
   - Monthly and yearly totals of layoffs.
   - Summarization of layoffs by stage (likely a reference to the company’s funding or business stage).
   2. Rolling Total: Using a CTE to compute rolling totals of layoffs over months.
   3. Top Companies per Year: Identifying the top 5 companies with the highest layoffs each year, leveraging a DENSE_RANK() window function.
This script is a solid mix of data cleaning, transformation, and exploratory analysis, which helps in understanding the patterns and trends within the layoff data.

