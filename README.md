# Customer Segmentation Analysis for Subscription Services 

## Table of Content 
---
[Project Overview](#project-overview)

[Data Source](#data-source)

[Tools Used](#tools-used)

[Data Cleaning and Preparation](#data-cleaning-and-preparation)

[Exploratory Data Analysis](#exploratory-data-analysis)

[Data Analysis](#data-analysis)

[Visualization](#visualization)

[Result and Findings](#result-and-findings)

[Recommendation](#recommendation)

[Limitations](#limitations)

### Project Overview
---
This project aims to analyze customer data for a subscription based service to identify distinct customer segment, understand their behavior and track trends in subscriptions and cancellations. This analysis will identify and characterize customer segments based on demographic and behavioral factor, analyze subscription patterns and develop data driven recommendations to enhance customer experience and retention. 

### Data Source
---
The initial data used for this Customer Segmentation Analysis project,  ‘Customer Data’, was obtained from ‘LITA Capstone Dataset’ provided by The Incubator Hub.

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
- What are the subscription patterns in the customer data?
- What is the average subscription duration?
- What are the most popular subscription types?
- ⁠What is the total number of customers from each region
- ⁠Which subscription type has the most customers?
- ⁠How many customers canceled their subscription within 6 months?
- ⁠How many customers have subscriptions longer than 12 months?
- ⁠What is the total revenue by subscription type?
- ⁠Which are the top 3 regions by subscription cancellations?
- ⁠What is the total number of active and canceled subscriptions?

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
3. Power Bi
- Measures
```DAX 
Total Cancellations = Cancellations / Count(CustomerID)
```

- Conditional column 

### Visualization 

- Pivot Tables Summarizations

![Customer_data_pivot](https://github.com/user-attachments/assets/154bd7f6-0acc-4088-a6af-2e1a7dc50410)

![Customer_pivot_table](https://github.com/user-attachments/assets/ac4f1235-4206-42ee-9a91-53e4bba5bb70)

![Customer_data_pivot_table](https://github.com/user-attachments/assets/b8f8fdc6-0717-4047-b108-ff73d53c93e9)

- Metrics with Excel Formula

![CUS_DATA_PIVOT](https://github.com/user-attachments/assets/c1e33a04-a0d2-4f26-8e38-0e1bcb856a47)

- Structured Query Summarizations(SQL) Summarizations

![SQL QUERY1](https://github.com/user-attachments/assets/9189020f-35bc-4fb3-9219-7d93931826ec)

![SQL_QUERY2](https://github.com/user-attachments/assets/529634a2-d23b-4d0f-80bb-d893830fe2aa)

![SQL_QUERY 3](https://github.com/user-attachments/assets/5fcc0518-537b-488d-8d40-a42cd97fecf4)

![SQL_QUERY_4](https://github.com/user-attachments/assets/6c44409c-e30a-4774-ba0b-70c4f382f40c)

- Customer Data Dashboard

![Customerdata](https://github.com/user-attachments/assets/4632085f-c591-476d-ae4c-1482174794d5)

- Customer Data Table and Chart

![Customer_data_table](https://github.com/user-attachments/assets/3581f54b-e75b-4cbf-8667-342e4536bb8d)


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
To ensure accuracy and reliability of the analysis, i had to remove all zero-value  were excluded from the dataset, as they could potentially skew the results and misinterpret true trends and patterns.
