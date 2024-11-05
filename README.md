# Customer Segmentation Analysis for Subscription Services 

## Table of Content 
---
[Project Overview](#project-overview)

[Data Source](#data-source)

[Tools Used](#tools-used)

[Data Cleaning and Preparation](#data-cleaning-and-preparation)

[Exploratory Data Analysis](#exploratory-data-analysis)

[Data Analysis](#data-analysis)

[Visualization])(#visualization)


### Project Overview
---
This project aims to analyze customer data for a subscription based service to identify distinct customer segment, understand their behavior and track trends in subscriptions and cancellations. This analysis will identify and characterize customer segments based on demographic and behavioral factor, analyze subscription patterns and develop data driven recommendations to enhance customer experience and retention. 

### Data Source
---
The data for this Customer Segmentation Analysis project,  ‘Customer Data’, was obtained from ‘LITA Capstone Dataset’ provided by The Incubator Hub.

### Tools Used
---
- Excel

  1. For Data Cleaning
  2. For Data Analysis
- Structured Query Language (SQL) - For Querying of Data

- Power Bi - For Creating Reports and visualizations

- Github - For Portfolio Building

### Data Cleaning and Preparation 
---
The following Initial data preparation steps were taken: 
1. Data loading and inspection
2. ⁠Removing duplicates and checking for missing values 
3. ⁠Data  Cleaning and Formatting

### Exploratory Data Analysis 
---
The following questions were answered: 
1. What are the subscription patterns in the customer data?
2. What is the average subscription duration?
3. What are the most popular subscription types?
4. ⁠What is the total number of customers from each region
5. ⁠Which subscription type has the most customers?
6. ⁠How many customers canceled their subscription within 6 months?
7. ⁠How many customers have subscriptions longer than 12 months?
8. ⁠What is the total revenue by subscription type?
9. ⁠Which are the top 3 regions by subscription cancellations?
10. ⁠What is the total number of active and canceled subscriptions?

### Data Analysis 
---
Some of the codes and features utilized to extract insights from the customer data include the following: 
1. Excel
- Pivot tables
```Excel 
= AVERAGE(Subscription duration in days I:I) 
```
``` Excel
=COUNTIF(Subscription type, premium, revenue)
```
2. Structured Query Language
```SQL
SELECT REGION, COUNT(CUSTOMERID) AS TOTALCUSTOMERS
FROM [dbo].[Capstone_Customer_Data_Project]
GROUP BY REGION
```

``` SQL
SELECT TOP 1 SUBSCRIPTIONTYPE, COUNT(CUSTOMERID) AS CUSTOMERS_NO
FROM [dbo].[Capstone_Customer_Data_Project]
GROUP BY SUBSCRIPTIONTYPE
```

```SQL
SELECT CUSTOMERID, SUBSCRIPTIONSTART, SUBSCRIPTIONEND
FROM [dbo].[Capstone_Customer_Data_Project]
WHERE DATEDIFF(MONTH, SUBSCRIPTIONSTART, SUBSCRIPTIONEND) <= 6
AND CANCELED = 1
```
3. PowerBi

```DAX 
Total Cancellations = Cancellations / Count(CustomerID)
```

- Conditional column and measures

### Visualization 

### Result and Findings 
---
The result of the analysis are summarized as follows: 

The average customer value is substantial indicating potential for significant revenue growth. Regional customer distribution is relatively even, with East, North, South, and West regions having similar customer counts. 
Cancellation rate is high, highlighting the need for effective retention strategies. 
Basic subscription type generates the most revenue followed by Standard and Premium each. 
Top 10 customers account for significant revenue emphasizing the importance of targeted customer retention.

### Recommendation 
---
Based on the analysis, I recommend the following actions:

Implement targeted retention strategies to reduce high cancellation rates.

Enhance Basic subscription features to maintain competitive edge.

Conduct regular customer feedback surveys to inform retention strategies.

Monitor and analyze cancellation reasons.

Develop tailored retention programs for top 10 customers, including:

### Limitations:
---
To ensure accuracy and reliability of the analysis, zero-value data points were excluded from the dataset, as they could potentially skew the results and misinterpret true trends and patterns.
