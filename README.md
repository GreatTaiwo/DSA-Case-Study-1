# DSA-Case-Study-1

This is a project from Digital Skillup Africa (DSA) Data Analysis Class with the Incubator Hub. The training focused on Microsoft Excel, SQL and Power BI. This particular repository is for the Capstone Project titled Case study 1, an Excel project.  

## Project Topic: Case Study 1: Amazon Product Review Analysis

### Project Overview

This project aims to generate insights that can guide product improvement, marketing strategies, and customer engagement.

## Data Sources

The primary source of the data used was 'Amazon case study Microsoft Excel Worksheet' from Amazon product pages, it includes:
- Product details: name, category, price, discount, and ratings
- Customer engagement: user reviews, titles, and content
- Each row represents a unique product, with aggregated reviewer data, stored as comma-separated values
  - Total Records: 1,465 rows
  - Total Fields: 16 columns
- File: https://github.com/GreatTaiwo/DSA-Case-Study-1/blob/main/Amazon%20case%20study.xlsx
 
## Tools Used

Ms Excel for Data cleaning and analysis [Download here](https://www.microsoft.com/en-us/microsoft-365/excel)

## Data Cleaning and Preparation

1. Opening of file and converting the dataset to table so as to make it structured.
The dataset needed no much cleaning except for the above and the change of a symbol to number.

## Exploratory Data Analysis (EDA)
EDA involved the exploring of the Data to answer some questions using pivot tables and calculated columns where necessary to answer the following:
1. What is the average discount percentage by product category?
2. How many products are listed under each category?
3. What is the total number of reviews per category?
4. Which products have the highest average ratings?
5. What is the average actual price vs the discounted price by category?
6. Which products have the highest number of reviews?
7. How many products have a discount of 50% or more?
8. What is the distribution of product ratings (e.g., how many products are rated 3.0, 4.0, etc.)?
9. What is the total potential revenue (actual_price × rating_count) by category?
10. What is the number of unique products per price range bucket (e.g., <₹200, ₹200–₹500, >₹500)?
11. How does the rating relate to the level of discount?
12. How many products have fewer than 1,000 reviews?
13. Which categories have products with the highest discounts?
14. Identify the top 5 products in terms of rating and number of reviews combined

## Data Analysis

- Pivot tables were created from the data and in answering some questions, calculated columns were created like in the case of questions 9-11 and 14.
* NB: In the file, some columns were created which were unnecessary such as New Product ID and New Review ID. I realized eventually that the count of Product ID and Review ID could have been used. I guess that was a rookie's mistake 😃!
- In creating these calculated columns, here are the codes used:
  - Question 9: =[@[actual_price]]*[@[rating_count]]
  - Question 10: =IF([@[discounted_price]]<200, "<200", IF([@[discounted_price]]<=500, "200-500", ">500"))
  - Question 11: = IF([@[discount_percentage]] <10%, "0-10%", IF([@[discount_percentage]] <=20%, "11-20%", IF([@[discount_percentage]]<= 30%, "21-30%", IF([@[discount_percentage]]<=40%, "31-40%", IF([@[discount_percentage]]<=50%, "41-50%", IF([@[discount_percentage]]<=60%, "51-60%", IF([@[discount_percentage]]<=70%, "61-70%", IF([@[discount_percentage]]<=80%, "71-80%", IF([@[discount_percentage]]<=90%, "81-90%", IF([@[discount_percentage]]<=100%, "91-100%"))))))))))
  - Although for question 7, a calculated column was created using = IF([@[discount_percentage]] >= 50%, "1", "0"), but this was not used, rather, filter was used on the pivot table. 

## Interpretation of Result

The dashboard showed charts that I believe would help guide product improvement, marketing strategies, and customer engagement:
