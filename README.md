# Customer-Segmentation-for-a-Subscription-Service
## Table of Contents
1. [Executive summary](executivesummary)
2. [Project background](projectbackground)
3. [Data overview](dataoverview)
4. [Methodology](methodology)
5. [Excel Pivot Tables and Charts](excelpivottablesandcharts)
6. [Data analysis](data-analysis)
7. [Power BI Visualization](powerbivisualization)
8. [Conclusion](conclusion)

## Executive Summary
This project presents an in-depth analysis of customer segmentation for a subscription service, using Excel, SQL, and Power BI. By analyzing customer behavior data, the project aims to identify trends in subscription preferences, cancellations, and renewals. These insights are expected to help improve customer retention and enable targeted marketing efforts for the subscription service, enhancing overall engagement and satisfaction.
## Project Background
**Context**

In the competitive subscription service industry, effective customer segmentation is essential for personalizing customer experiences and retaining users. This analysis helps the service understand various customer segments, empowering the company to tailor offerings and marketing strategies based on identified trends.

**Goal**

The project’s goal is to segment customers by analyzing behavior patterns and subscription data, particularly focusing on:
- Tracking popular subscription types and usage patterns.
- Identifying trends in cancellations and renewals.
- Gaining insights into customer engagement and satisfaction.
## Data Overview
**Data Sources**

The dataset, provided by an instructor, includes simulated data for a fictional subscription service, representing customer and subscription details. This data allows practice of segmentation techniques and development of data analysis and visualization skills.

**Data Structure**

The dataset includes the following columns:
- Customer ID: Unique identifier for each customer.
- Region: Customer’s geographical location.
- Subscription Type: Type of subscription held by the customer.
- Subscription Start and Subscription End: Dates marking the start and end of each subscription.
- Cancelled: Binary indicator for subscription cancellations.
- Renewal: Binary indicator for renewals.
- Average Subscription Duration: Average time a customer has held a subscription.
## Methodology
The methodology for this customer segmentation analysis involved several key steps, utilizing Excel, SQL, and Power BI to derive insights from the customer dataset.

**Data Preparation**
	
The initial dataset provided was cleaned and pre-processed to remove any inconsistencies or missing values. This step ensured data integrity for subsequent analyses.
	
**Data Exploration**

In the data exploration phase, various techniques were employed to gain insights into the dataset. Descriptive statistics were calculated for key numerical columns, providing an overview of customer engagement trends. Specific tasks included:
- Identifying Popular Subscription Types
- Finding Subscription Patterns
- Finding the most popular subscription type by the number of customers.
- Identifying the top three regions by subscription cancellations.
- Finding customers who canceled their subscription within six months.
- Calculating average subscription duration for all customers.
- Finding customers with subscriptions longer than twelve months.
- Calculating total revenue by subscription type.
- Finding the total number of active and canceled subscriptions.
## Excel Pivot Tables and Charts
![image](https://github.com/user-attachments/assets/f64c1855-7784-46af-99a4-5601881e5e48)

This Pivot table represent the most popular subscription type.

![image](https://github.com/user-attachments/assets/88bf139e-9348-47a9-b800-c94eca44db83)

Accompany the pivot table,this chart visually represent the most popular subscription type.

![image](https://github.com/user-attachments/assets/6f2c7837-6af8-4f07-be94-35c0329db106)

This pivot table represent the Average subscription duration.

![image](https://github.com/user-attachments/assets/1c8806de-f615-482e-8ab9-e8924abb8be8)

Accompany the pivot table, this chart visually represent the average subcription duration.

![image](https://github.com/user-attachments/assets/57740a7c-dbd1-4c79-8268-8571dab39445)

This pivot table represent the subscription pattern of cancelled data plan by region.

![image](https://github.com/user-attachments/assets/11c5c928-fc16-450b-b880-6891e10c27b4)

Accompany the pivot table, this chart visually represent the subscription pattern of cancelled data plan by region.

## Data Analysis
This phase involved executing SQL queries to extract critical insights, such as retrieving the total number of customers in each region,finding the most popular subsription type by the number of customers and so on.

Below are some of the queries ran during the analysis;
### Query 1:
```sql
select region,			
count (customerid) as Total_customer			
from csvcapstoneprojectcustomerdata			
group by region			
```
**Purpose** This query retrieves the total number of customers in each region
### Query 2:
```sql
select subscriptiontype,			
count(customerid) as 			
number_of_customers			
from csvcapstoneprojectcustomerdata			
group by subscriptiontype			
order by number_of_customers desc			
```
**Purpose** This query retrieves the most popular subscription type by the number of customer
### Query 3:
```sql
 select customerid				
 from csvcapstoneprojectcustomerdata				
 where subscriptionend-subscriptionstart <=180				
 and canceled=true
```
**Purpose** This query retrieves the customers who cancelled their subscription within six month
### Query 4:
```sql
count(*) as cancellation			
from csvcapstoneprojectcustomerdata			
where canceled=true			
group by region			
order by canceled DESC			
limit 3			
```
**Purpose** This query retrieves the top 3 regions by subscription cancellation
## Power BI Visualization
![image](https://github.com/user-attachments/assets/f4dfc3d5-c219-4bc1-8632-8cf49b8e726c)

## Conclusion
The Customer Segmentation for a Subscription Service project effectively uncovers patterns and trends within customer subscription data. Through segmentation analysis, it identifies popular subscription types, customer usage patterns, and regions with high cancellation rates. By pinpointing customers who cancel early or hold longer subscriptions, the analysis provides valuable insights for retention strategies. The SQL-driven approach allows for precise data extraction, supporting a clear understanding of customer behavior.
The findings suggest targeted marketing opportunities to retain at-risk customers, particularly in regions with higher cancellation rates, and to enhance engagement with popular subscription types. By leveraging these insights, the subscription service can better tailor its offerings, ultimately aiming to boost customer satisfaction and long-term retention.
