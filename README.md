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

<img width="661" height="311" alt="image" src="https://github.com/user-attachments/assets/21b3fc69-1378-41fd-bf57-4722fdcfabaf" />
<img width="533" height="326" alt="image" src="https://github.com/user-attachments/assets/97c817c8-a906-44d1-86b9-14f8d0c2599b" />
<img width="827" height="307" alt="image" src="https://github.com/user-attachments/assets/c49c3ed0-4b15-4be7-92b7-71879f925050" />
<img width="788" height="309" alt="image" src="https://github.com/user-attachments/assets/512d82a3-843d-4b0b-9a9e-2ee71e0ad108" />
<img width="587" height="287" alt="image" src="https://github.com/user-attachments/assets/21c45273-86a0-42e7-b9d2-767b9cc77962" />
<img width="521" height="299" alt="image" src="https://github.com/user-attachments/assets/40564889-9d7b-4efa-ba42-862636e75207" />
<img width="846" height="251" alt="image" src="https://github.com/user-attachments/assets/9e1de989-5cfc-4e0c-bc9f-98824491395a" />













  
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

```
countdeliv=deliv["customer_city"].value_counts()
countdeliv

stud.groupby(["customer_id"])["total_price"].mean()

setq=stud.groupby(["month"])["total_price"].sum(numeric_only=True).reset_index()
setq

stud.groupby("customer_gender")["total_price"].sum().reset_index()

mos=stud.groupby(["delivery_status"])["quantity"].sum().reset_index(name="most")
mos
mos.sort_values(by="most",ascending=False)

freq=stud.groupby(["product_name"])["total_price"].sum(numeric_only=True).reset_index()
tot=freq.sort_values(by="total_price")
tot

freq=stud.groupby(["payment_method"])["total_price"].sum(numeric_only=True).reset_index()
pri=freq.sort_values(by="total_price")

setq=stud.groupby(["delivery_status"])["total_price"].sum(numeric_only=True).reset_index()
pric=setq.sort_values(by="total_price")

setq=stud.groupby(["customer_city"])["total_price"].sum(numeric_only=True).reset_index()
city=setq.sort_values(by="total_price")

setq=stud.groupby(["month"])["total_price"].sum(numeric_only=True).reset_index()
mon=setq.sort_values(by="total_price")

top_cities = stud[stud['delivery_status'] == 'Delivered']['customer_city'].value_counts().head(10)

```




### Data Analysis
Various analyses were performed using grouping, filtering, and aggregation to extract top cities, delivery frequencies, price distributions, and payment method.


### Core Insights
- Most orders were successfully delivered, with few returns or cancellations.
- Certain cities dominated the number of deliveries, indicating regional demand patterns.
- Total price by month showed total sales lesser than average in most months.
- Total price by month showed that most cities generated a higher revenue that average.
- Some payment methods are associated with higher order values.


### Recommendations 
- Focus marketing efforts on top cities with high delivery volume.
- Encourage use of high-performing payment methods through incentives.
- Investigate causes of failed deliveries to improve logistics.
- Explore strategies to boost high-value purchases.
