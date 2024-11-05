# CAPSTONE-PROJECT-CUSTOMER_DATA-

## Project Overview 

This project entails the analysis of customer data for a subscription service, aiming to identify various segments and trends. The goal is to understand customer behavior, evaluate different subscription types, and pinpoint key patterns in cancellations and renewals. The final output will be a Power BI dashboard showcasing the findings.

## Basic statistical data 
Total Revenue : 67.5 Million
Average Revenue : 1999
Average Duration : 365.35
Total Customer : 33787
Total Order : 33787

## Data Collection
The data used was collected and complied through transaction logging. This ensures that the dataset represents an accurate record of customer interactions and purchasing patterns over a year and eight months.


## Tools Used
- Microsoft Excel
- SQL
- Power Bi

## EXPLORATORY DATA ANALYSIS (EDA)

After cleaning the data in Excel and creating pivot tables, it was exported to SQL for deeper analysis and then to Power BI for dashboard creation.

1. Descriptive Statistics: Excel calculated average and total sales by region and product, while SQL queries provided insights into total revenue and monthly sales. Power BI displayed key metrics like total revenue and average sales through summary cards.


2. Data Filtering and Segmentation: Excel's filtering and pivot tables enabled segmentation by region and product, uncovering targeted insights. SQL used WHERE and GROUP BY clauses for specific filtering, while Power BI utilized slicers for dynamic analysis by region and year.


3. Dashboard Creation: Excel's pivot tables structured summaries for dynamic updates. SQL aggregated data served as a foundation for dashboards, ensuring integration with other tools. Power BI’s interactive dashboards offered real-time insights with slicers for in-depth analysis of customer and product dimensions.

  
## Column Descriptions

CustomerID: A distinct identifier for each customer, ensuring unique tracking.

CustomerName: The customer’s name, presented in an anonymized format when necessary for privacy.

Region: The geographical classification of the customer’s location (e.g., North, South, East, West).

SubscriptionType: The category of subscription plan that the customer has chosen (e.g., Basic, Premium).

SubscriptionStart: The date marking the beginning of the customer’s subscription journey.

SubscriptionEnd: The date signaling the conclusion of the customer’s subscription.

Canceled: A boolean indicator showing whether the subscription has been terminated (TRUE or FALSE).

Revenue: The total revenue attributed to the customer's subscription.

Subscription Duration: The length (in days) of the subscription period from start to end.

## Data Cleaning and Preparation

In this phase, we undertake several critical actions:

1. Data Loading and Inspection: We begin by loading the dataset and performing an initial inspection to understand its structure and contents.


2. Handling Missing Variables: We address any missing values in the dataset to ensure completeness and accuracy.


3. Data Cleaning and Formatting: We clean the data by correcting inconsistencies and formatting it to meet analytical standards.

## Data Analysis and Insight Generation

This Visualization reveals some intriguing patterns and trend from understanding customer behavior, tracking subscription types, and identifying key trends in cancellations and renewals of the various subcription types available in the company.

SUBSCRIPTION TREND : Subscription numbers showed fluctuations over time, monnthly, quarterly and yearly. There was a steady flow of revenue monthly until it declined in the month of september, it droped from 6.75 Million in August to 3.37 Million in September. Quarterly, there was a steady trend from the first to the second quarter but by the third quarter it declined from 20 Million to 16 Million and to 10 MIllion by the forth quarter. And finally yearly, from 2022 to 2023 there was a decline from 40 Million to 27 Million. This implies the purchases decline after a period of time. RECOMMENDATION : Increase marketing efforts during peak periods to capitalize on natural customer interest. And introduce targeted promotions and membership discounts during slower periods to encourage new sign-ups.
Sql 2 project( Based on Capstone Customer Data)

```
Select  region, count(distinct Customerid) as total_customers 
from [dbo]
Group by region;
```
```
Select top 1 subscriptiontype, count(distinct customerid) as total_customers
From [dbo]
Group by subscriptiontype 
Order by total_customers desc;
```
```
Select customerid,
From [dbo]
Where datadiff(month, subscriptionstart, subscriptionend) <= 6;
```
```
Select avg(datediff(day, subscriptionstart, subscriptionend)) as avg_subscription_duration
From [dbo]
```
```
Select customerid
From [dbo]
Where datediff(month, subscriptionstart  subscriptionend) > 12;
```

```
Select subscriptiontype,
Sum(revenue) as total_revenue 
From [dbo]
Group by subscriptiontype;
```

```
Select top 3 region,
Count(*) as subscriptionend_count
From [dbo]
Where subscriptionend is null
Group by region
Order by subscriptionend_count desc;
```

























