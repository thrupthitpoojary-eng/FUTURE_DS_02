# Customer Churn & Retention Analysis

## 1. Project Overview

This project focuses on analyzing customer churn data to understand customer retention patterns and identify factors associated with customers leaving a subscription-based service.

Customer churn is an important concern for subscription-based businesses because losing customers can affect business growth and revenue. Analyzing customer data helps businesses understand customer behaviour and identify patterns related to churn.

This project was carried out using Power BI Desktop. The dataset was analyzed, important customer metrics were calculated, and an interactive dashboard was created to present the results through different visualizations.

## 2. Project Objectives

The main objectives of this project are:

- Calculate the total number of customers in the dataset.
- Identify the number of churned and retained customers.
- Calculate the overall customer churn rate and retention rate.
- Analyze customer churn based on subscription type and contract length.
- Study churn patterns based on customer details such as gender, support calls, payment delay and usage frequency.
- Compare the average tenure of churned and retained customers.
- Create an interactive Power BI dashboard to present the analysis clearly.
- Use visualizations to make customer churn patterns easier to understand.

## 3. Dataset Description

The dataset used for this project is `customer_churn_dataset-testing-master.csv`.

It contains 64,374 customer records and 12 columns. Each row represents a customer's information, including personal details, subscription information, usage behaviour and churn status.

The dataset contains the following columns:

| Column Name | Description |
|---|---|
| CustomerID | Unique identification number of each customer |
| Age | Age of the customer |
| Gender | Gender of the customer |
| Tenure | Duration of the customer's association with the service |
| Usage Frequency | Frequency of service usage |
| Support Calls | Number of support calls made by the customer |
| Payment Delay | Number of days of payment delay |
| Subscription Type | Type of subscription (Basic, Standard, Premium) |
| Contract Length | Contract duration (Monthly, Quarterly, Annual) |
| Total Spend | Total amount spent by the customer |
| Last Interaction | Time since the customer's last interaction |
| Churn | Indicates whether the customer left the service (1) or stayed (0) |

The Churn column is particularly important for this analysis because it helps distinguish between customers who have left the service and those who are still using it.

## 4. Tools and Technologies Used

The following tools and technologies were used to complete the project:

- **Power BI Desktop:** Used to analyze the customer data and create an interactive dashboard with charts, KPI cards and slicers.
- **Power Query:** Used for importing, checking and preparing the dataset before analysis.
- **DAX (Data Analysis Expressions):** Used to create calculated measures for customer count, churn rate, retention rate and average tenure.
- **CSV Dataset:** Used as the source of customer information for the analysis.

## 5. Data Import and Preparation

The dataset was imported into Power BI Desktop and prepared before creating the dashboard.

The following steps were performed:

1. Opened Power BI Desktop and selected the option to import data from a text/CSV file.
2. Selected the `customer_churn_dataset-testing-master.csv` dataset.
3. Checked the column names and data types to ensure that the data was loaded correctly.
4. Verified the dataset for missing values and duplicate customer records.
5. Checked the CustomerID column to ensure that each customer had a unique identification number.
6. Ensured that the Churn column was correctly interpreted, where 1 represents churned customers and 0 represents retained customers.
7. Loaded the prepared dataset into Power BI for further analysis.

This preparation helped ensure that the data was suitable for creating measures and visualizations.

## 6. DAX Measures

DAX (Data Analysis Expressions) was used to create measures for calculating the main customer metrics.

The following measures were created:

**Total Customers**

Calculates the total number of unique customers in the dataset.

```DAX
Total Customers =
DISTINCTCOUNT('customer_churn_dataset-testing-master'[CustomerID])
```

**Churned Customers**

Calculates the number of customers who have left the service. The Churn value is 1 for these customers.

```DAX
Churned Customers =
CALCULATE(
    COUNTROWS('customer_churn_dataset-testing-master'),
    'customer_churn_dataset-testing-master'[Churn] = 1
)
```

**Retained Customers**

Calculates the number of customers who are still using the service. The Churn value is 0 for these customers.

```DAX
Retained Customers =
CALCULATE(
    COUNTROWS('customer_churn_dataset-testing-master'),
    'customer_churn_dataset-testing-master'[Churn] = 0
)
```

**Churn Rate**

Calculates the percentage of customers who have left the service.

```DAX
Churn Rate =
DIVIDE([Churned Customers], [Total Customers], 0)
```

**Retention Rate**

Calculates the percentage of customers who have continued using the service.

```DAX
Retention Rate =
DIVIDE([Retained Customers], [Total Customers], 0)
```

**Average Tenure**

Calculates the average tenure of all customers in the dataset.

```DAX
Average Tenure =
AVERAGE('customer_churn_dataset-testing-master'[Tenure])
```

These measures were used to display important customer metrics in the dashboard.

## 7. Key Performance Indicators

The dashboard displays the following key performance indicators (KPIs):

| KPI | Result |
|---|---:|
| Total Customers | 64,374 |
| Churned Customers | 30,493 |
| Retained Customers | 33,881 |
| Churn Rate | 47.37% |
| Retention Rate | 52.63% |
| Average Tenure | 32.0 |

These KPIs provide an overview of customer churn and retention. They help compare the number of customers who have left the service with those who have continued using it.

## 8. Dashboard Visualisations

The Power BI dashboard includes:

1. **KPI Cards:** Total customers, churned customers, retained customers, churn rate and average tenure.
2. **Churned Customers by Subscription Type:** Compares churn across Basic, Standard and Premium plans.
3. **Churned Customers by Contract Length:** Compares Monthly, Quarterly and Annual contracts.
4. **Churned Customers by Gender:** Shows churned customer counts by gender.
5. **Churn by Support Calls:** Explores churn across different support call values.
6. **Churn by Payment Delay:** Compares churn across payment delay values.
7. **Churn by Usage Frequency:** Explores churn across usage frequency values.
8. **Average Tenure by Churn Status:** Compares the average tenure of churned and retained customers.
9. **Churn Rate Charts:** Compares churn rates by subscription type, contract length and gender.
10. **Dropdown Slicers:** Filters the dashboard by subscription type, contract length and gender.

The dashboard combines different types of charts and KPI cards to make the information easier to understand. Dropdown slicers allow users to select different categories and explore the data interactively.

## 9. Conclusion

This project provided an opportunity to understand customer churn and retention through practical data analysis using Power BI Desktop.

The customer dataset was imported and prepared before creating DAX measures to calculate important metrics such as total customers, churned customers, retained customers, churn rate, retention rate and average tenure.

Different visualizations were created to compare churn across subscription types, contract lengths, gender, support calls, payment delays and usage frequency. KPI cards and dropdown slicers were also added to make the dashboard interactive and easier to explore.

Through this project, I gained practical experience in working with a real-world-style dataset, preparing data, creating DAX measures and designing an interactive dashboard using Power BI. It also helped me improve my understanding of data analysis and visualization.
