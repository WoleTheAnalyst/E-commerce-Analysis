# E-Commerce Customer Order Analysis

## Table of Contents
- [Project Overview](#project-overview)
- [Objectives](#objectives)
- [Data Source](#data-source)
- [Tools](#tools)
- [Data Cleaning](#data-cleaning)
- [Data Exploratory Analysis](#data-exploratory-analysis)
- [Data Analysis](#data-analysis)
- [Core Insights](#core-insights)
- [Recommendations](#recommendations)

  
## Project Overview
This project analyzes an e-commerce orders dataset to derive insights about customer behavior, sales distribution, delivery performance, and payment preferences. The primary goal is to uncover actionable trends that can guide business strategy.


<img width="712" height="299" alt="Screenshot 2025-07-23 175221" src="https://github.com/user-attachments/assets/1d43d473-a479-4c3a-85d0-2ce9fc78f975" />

  
### Objectives
- Understand the distribution of order deliveries across cities and statuses.
- Analyze customer purchasing patterns based on total price and payment methods.
- Identify the top-performing customer locations.
- Provide recommendations to optimize delivery and sales performance.


### Data Source
The dataset used is ecommerce_orders_dataset (1).csv, which includes details such as product name, total price, payment type, customer city, and delivery status.

### Tools
- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Jupyter Notebook


  ### Data Cleaning
Initial cleaning included filtering the dataset for valid entries, handling missing values (if any), and focusing on relevant columns like delivery status, customer city, total price, and payment type.


### Data Exploratory Analysis
This involved generating summary statistics, counting deliveries by cities, examining distribution of prices, and exploring categorical fields like payment type and delivery status.

```countdeliv=deliv["customer_city"].value_counts()
countdeliv

stud.groupby(["customer_id"])["total_price"].mean()

cancel=stud.loc[stud["delivery_status"]=="Cancelled"]
cancel
cancel_1=cancel["product_name"].value_counts()
cancel_1.idxmax()

mos=stud.groupby(["delivery_status"])["quantity"].sum().reset_index(name="most")
mos
mos.sort_values(by="most",ascending=False)
```


### Data Analysis
Various analyses were performed using grouping, filtering, and aggregation to extract top cities, delivery frequencies, price distributions, and payment behavior.


### Core Insights
- Most orders were successfully delivered, with few returns or cancellations.
- Certain cities dominated the number of deliveries, indicating regional demand patterns.
- Total price showed right-skewed distribution—few high-value orders exist.
- Some payment methods are associated with higher order values.


### Recommendations 
- Focus marketing efforts on top cities with high delivery volume.
- Encourage use of high-performing payment methods through incentives.
- Investigate causes of failed deliveries to improve logistics.
- Explore strategies to boost high-value purchases and retain loyal customers.
