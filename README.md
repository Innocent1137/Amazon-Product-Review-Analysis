# Amazon Product Review Analysis
An analysis of Amazon product reviews using exploratory data analysis, sentiment classification, and visualization techniques.

### 1. Project Overview

This project analyzes Amazon product review data using Pivot Tables. It explores key business metrics such as average discounts, ratings, review counts, and potential revenue to uncover trends and insights from customer behavior.

### 2. Data Source
Data Source: The parmary dataset used for the analysis is "Amazon case study.xlsx" provided by DSA Data_file containing analytical exercises, such as product performance, review sentiment, and pricing

### TOOLS

Ms Excel for Data cleaning [Download Excel (Microsoft 365)](https://www.microsoft.com/en-us/microsoft-365/excel)
 - for Data Collection
 - for Data cleaning
     1. Data manipolation
     2. Data Manching
 
### 3. Data Cleaning/Preparation


In the initial data preparation phase, i performed the following task;
1. Data Loading and inspecting.
2. Handling missing values.
3. Data cleaning and formatting

### 4. Exploratory Data Analysis

EDA involved exploring the sales data to answer the Question, such as:

- What is the average discount percentage by product category?
- How many products are listed under each category?
- What is the total number of reviews per category?
- Which products have the highest average ratings?
- What is the average actual price vs the discounted price by category?
- Which products have the highest number of reviews?
- How many products have a discount of 50% or more?
- What is the distribution of product ratings?
- What is the total potential revenue by category?
- How many products fall into different price buckets?
- How does rating relate to the level of discount?
- How many products have fewer than 1,000 reviews?
- Which categories have the highest discounts?
- What are the top 5 products by combined rating and review count?

### Data Analysis

Include some interersting code/ features worked with

```This is Generated Using Excel Pivot Tables

1. Average Discount Percentage by Category
- Insert Pivot Table
- **Rows**: `category`
- **Values**: `discount_percentage` → Summarize by **Average`

2. Number of Products by Category
- Insert Pivot Table
- **Rows**: `category`
- **Values**: `product_id` → **Count**
- 🔹 To get distinct products: check "Add this data to the Data Model" and use **Distinct Count**

3. Total Reviews per Category
- Insert Pivot Table
- **Rows**: `category`
- **Values**: `rating_count` → Summarize by **Sum**

4. Products with Highest Average Ratings
- Insert Pivot Table
- **Rows**: `product_name`
- **Values**: `rating` → **Average**
- 🔹 Sort descending to view highest-rated products

5. Average Actual Price vs Discounted Price by Category
- Insert Pivot Table
- **Rows**: `category`
- **Values**:
  - `actual_price` → **Average**
  - `discounted_price` → **Average**

6. Products with Highest Number of Reviews
- Insert Pivot Table
- **Rows**: `product_name`
- **Values**: `rating_count` → **Sum**
- 🔹 Sort descending

7. Products with ≥ 50% Discount
- Use Filter: `discount_percentage >= 0.5`
- Optionally add:
  - **Rows**: `product_name`
  - **Values**: `product_id` → Count

8. Distribution of Product Ratings
- Insert Pivot Table
- **Rows**: `rating`
- **Values**: `product_id` → **Count**

9. Total Potential Revenue by Category
- Add column in sheet:
  =actual_price * rating_count
- Insert Pivot Table
  - **Rows**: `category`
  - **Values**: your new `revenue` column → **Sum**

10. Products per Price Bucket
- Add column in sheet:
  =IF(discounted_price<200,"<₹200",IF(discounted_price<=500,"₹200–₹500",">₹500"))
- Insert Pivot Table:
  - **Rows**: `price_bucket`
  - **Values**: `product_id` → **Count**

11. Rating vs Discount (Scatter Plot)
- Select columns: `rating` and `discount_percentage`
- Insert → Scatter Chart
- Optional: Add **trendline**

12. Products with <1,000 Reviews
- Use Filter: `rating_count < 1000`
- Or:
  - **Rows**: `product_name`
  - **Values**: `rating_count`
  - Filter or sort accordingly

13. Categories with Highest Discounts
- Insert Pivot Table
- **Rows**: `category`
- **Values**: `discount_percentage` → **Average**
- 🔹 Sort descending

14. Top 5 Products by Composite Score
- Add column in sheet:
  =rating * LN(rating_count + 1)
- Insert Pivot Table:
  - **Rows**: `product_name`
  - **Values**: new column → **Average**
  - 🔹 Sort descending, pick top 5
```

### Result

## 📄 File: Amazon_Pivot_Insights_Results.xlsx

This Excel file includes **14 individual sheets**, each answering a specific business question using product and review data:

| Sheet Name                        | Insight Description                                                  |
|----------------------------------|-----------------------------------------------------------------------|
| Q1_Avg_Discount_By_Cat           | Average discount percentage by product category                      |
| Q2_Product_Count_By_Cat          | Number of unique products listed under each category                 |
| Q3_Reviews_By_Cat                | Total number of reviews per category                                 |
| Q4_Top_Avg_Rated_Products        | Top 10 products with the highest average rating                      |
| Q5_Price_Comparison              | Average actual vs discounted price by category                       |
| Q6_Most_Reviewed_Products        | Top 10 products with the most reviews                                |
| Q7_50pct_Discount_Count          | Total number of products with a discount of 50% or more              |
| Q8_Rating_Distribution           | Count of products per rating (e.g., 3.0, 4.0, etc.)                  |
| Q9_Revenue_By_Category           | Total estimated revenue per category (actual_price × rating_count)   |
| Q10_Price_Buckets                | Count of unique products by price range (<₹200, ₹200–₹500, >₹500)   |
| Q11_Rating_vs_Discount           | Table of rating and discount values (for scatter plot analysis)      |
| Q12_Under_1000_Reviews           | Products with fewer than 1,000 reviews                               |
| Q13_Top_Discount_Cats            | Categories with the highest average discounts                        |
| Q14_Top_Products_Score           | Top 5 products based on composite score: rating × log(review count)  |


