# E-commerce Report By Python
# X E-Commerce Report from 2016-2018

## Overview:

The X E-Commerces here is a small dataset used to demonstrate skills in both Big Data and Visualization platforms, languages and tools. The target of this project is to determine the business situation of the company after 3 years in operation by different factors and methods.

## Platforms, Languages and Tools:

- Python

- MySQL

- Power BI

## Dataset:

customers_dataset.xlsx
order_items_dataset.xlsx
order_payments_dataset.xlsx
order_reviews_dataset.xlsx
orders_dataset.xlsx
product_category_name_translation.xlsx
products_dataset.xlsx

## Variables:

*customers_dataset.xlsx*
customer_id | customer_unique_id| customer_zip_code_prefix | customer_city | customer_state

*order_items_dataset.xlsx*
order_id | order_item_id | product_id | seller_id | price | freight_value

*order_payments_dataset.xlsx*
order_id | payment_sequential | payment_type | payment_installments |payment_value

*order_reviews_dataset.xlsx*
review_id | order_id | review_score | review_comment_title | review_comment_message | review_creation_date | review_answer_timestamp

*orders_dataset.xlsx*
order_id | customer_id | order_status | order_purchase_timestamp | order_approved_at | order_delivered_carrier_date | order_delivered_customer_date | order_estimated_delivery_date

*product_category_name_translation.xlsx*
product_category_name | product_category_name_english

*products_dataset.xlsx*
product_id | product_category_name | product_name_length | product_description_length | product_photos_qty | product_weight_g | product_length_cm | product_height_cm | product_width_cm
## Conclusion:

From August 2017 to the present, the business situation has developed and grown steadily, resulting in a total revenue of 17.79 million. Freight costs accounted for 2.28 million, while goods sold amounted to 15.51 million. However, due to the availability of payment installment options, there was still an outstanding receivable amount of 2.58 million. The total number of orders reached 97,191, and the number of customer records reached 99,441.

Sales showed a consistent increase throughout the year, with the highest peak recorded in November 2017 at 1,575,685.79. In the following year, 2018, sales revenues remained relatively stable, ranging from 1.2 to 1.5 million per month. In terms of payment types, credit card transactions accounted for 76.84%, followed by cash payments at 19.92%, with a small portion attributed to debit and voucher payments. The review score charts revealed percentages of 56.19%, 18.89%, 8.45%, 3.54%, and 12.93% respectively, representing scores from 5 to 1. These figures provide an overview of the overall sales records, with further detailed analysis presented below.

## Table of Content:
1. Introduction
2. Question
3. Data Understanding
    a. Entity
    b. Attribute
    c. Entity Diagram
    d. Data Cleaning
4. Analyze Method
5. Analyzation
6. Final & Reccommendations


### 1. Introduction

The analysis performs the business overall of X-ecommerce company that was established in the end of 2016 up to 2018 with details of services, products, customer and sales overview. 

This report will also include the reccommendations for their performance.

### 2. Question

<img width="1332" alt="1  X-ecommerce question graph-Map 1" src="https://user-images.githubusercontent.com/108020327/236655402-8e018fdc-1b24-4f6a-b36a-b909e8d2aa09.png">

### 3. Data Understanding

#### a. Entity
<img src="https://github.com/Tann1901/e-commerce/blob/main/GIt%20ecommerce%20image/2.%20Entity.jpg" height="250">

#### b. Attribute
<img src="https://github.com/Tann1901/e-commerce/blob/main/GIt%20ecommerce%20image/3.%20Attribute.jpg" height="250">

#### c. Entity Diagram
<img src="https://github.com/Tann1901/e-commerce/blob/main/GIt%20ecommerce%20image/4.%20Entity%20diagram.jpg" height="250">


#### d. Data Cleaning
1. Create dataframe
```
import pandas as pd
import numpy as np

from google.colab import drive
drive.mount('/content/drive', force_remount=True)

#CREATE DATAFRAME
#Customer
customer_df = pd.read_excel('/content/dataset/customers_dataset.xlsx') 
#Product category
product_category_df = pd.read_excel('/content/dataset/product_category_name_translation.xlsx') #bảng dịch tên tiếng anh cho product
#Product_category_name
product_df = pd.read_excel('/content/dataset/products_dataset.xlsx')
#Order review
order_reviews_df = pd.read_excel('/content/dataset/order_reviews_dataset.xlsx')
#Order payment
order_payment_df = pd.read_excel('/content/dataset/order_payments_dataset.xlsx')
#Order
order_df = pd.read_excel('/content/dataset/orders_dataset.xlsx')
#Order item
order_item_df = pd.read_excel('/content/dataset/order_items_dataset.xlsx')
```
2. Check if dataframe is null and duplicated
<img src="https://github.com/Tann1901/e-commerce/blob/main/GIt%20ecommerce%20image/6.%20Check%20null.jpg" height="250">
3. Combine all related table to find null and duplicated values
<img src="https://github.com/Tann1901/e-commerce/blob/main/GIt%20ecommerce%20image/8.%20Check%20null%20value%20of%20combined%20table.jpg" height="250">
<img src="https://github.com/Tann1901/e-commerce/blob/main/GIt%20ecommerce%20image/9.%20Check%20duplicated%20value.jpg" height="90">
4. Check if order_id contains null and not_null product_id. (we need to consider if one order contains many null and not_null  values together that would make data biased)
<img src="https://github.com/Tann1901/e-commerce/blob/main/GIt%20ecommerce%20image/12.%20Check%20if%20order_id%20contain%20null%20and%20not%20null%20product_is.jpg" height="250">
5. Check if null_value of order_id can be removed
<img src="https://github.com/Tann1901/e-commerce/blob/main/GIt%20ecommerce%20image/13.%20Remove%20null%20value%20of%20order_id.jpg" height="250">
6. Remove null values of order_id
<img src="https://github.com/Tann1901/e-commerce/blob/main/GIt%20ecommerce%20image/14a.%20Check%20if%20order_id%20of%20product%20category%20in%20english%20contains%20null%20and%20not_null%20product_id.jpg" height="60">
<img src="https://github.com/Tann1901/e-commerce/blob/main/GIt%20ecommerce%20image/14b.%20Check%20if%20order_id%20of%20product%20category%20in%20english%20contains%20null%20and%20not_null%20product_id.jpg" height="350">
7. Check if order_id of English_product_category contains null and not_null product_id
<img src="https://github.com/Tann1901/e-commerce/blob/main/GIt%20ecommerce%20image/15.%20Check%20difference%20of%20revenue%20before%20and%20after%20removing%20products_id%20not%20in%20English.jpg" height="350">
8. Check difference of revenue before and after removing products_id not in English
<img src="https://github.com/Tann1901/e-commerce/blob/main/GIt%20ecommerce%20image/15.%20Check%20difference%20of%20revenue%20before%20and%20after%20removing%20products_id%20not%20in%20English.jpg" height="350">

9. Drop null values left 
<img src="https://github.com/Tann1901/e-commerce/blob/main/GIt%20ecommerce%20image/17.%20Drop%20null%20values%20left.jpg" height="450">

<img src="https://github.com/Tann1901/e-commerce/blob/main/GIt%20ecommerce%20image/17b.%20Drop%20null%20values%20left.jpg" height="450">
11. Update table/data after cleaning
<img src="https://github.com/Tann1901/e-commerce/blob/main/GIt%20ecommerce%20image/18a.%20Drop%20null%20values.jpg" height="450">

<img src="https://github.com/Tann1901/e-commerce/blob/main/GIt%20ecommerce%20image/18b.%20Update%20data%20after%20cleaning.jpg" height="450">

<img src="https://github.com/Tann1901/e-commerce/blob/main/GIt%20ecommerce%20image/18c.%20Update%20data%20after%20cleaning.jpg" height="450">

### 4. Analyze Method
Python, PowerBi, MySQL, Canva

### 5. Analyzation
#### SALES
In general, the total revenue reached 17.79 million, with freight accounted for 2.28 million and goods sold was 15.51 million. Due to the payment types were varied with payment installmentment, there was still 2.58 million receivable amount. Total order count reached 97191 and total customer records reached 99441. 
The sales were increasing throughout the year with peak recorded in November, 2017 at 1,575,685.79. In the latest year - 2018, the sales revenues were more stable throughout the months in the range of 1.2 - 1.5 million.  Closely look at payment type, 76.84% were credit card, 19,92% was cash and a small portion of debit and voucher. The review score charts also showed 56.19%, 18.89%, 8.45%, 3.54% and 12.93% prespectively from 5-1. These numbers presented the overall sales records with further details analyzed below.
<img src="https://github.com/Tann1901/e-commerce/blob/main/GIt%20ecommerce%20image/Sales.jpg" height="450">

#### PRODUCT
The graph shows highest proportion product group revenue are: health_beauty, bed_bath_table, watch_gifts, computers_accessories, sport_leisure ranging from 7.06%-8.76%. These belong to low average price group and and with average payment settlement at 2-4 times. Average delivery fee for these items are in range of $16-18.9.

In contrast, the highest average prices belong to the group computers, small_appliances_home_oven_and_coffee, home_appliances_2, agro_industry_and_commerce. These group also come with high freight and payment installment times with average from 3-6 imstallment period. These categories also fell in low selling rate at below 1% while delivery fee is in range $36-48. 

<img src="https://github.com/Tann1901/e-commerce/blob/main/GIt%20ecommerce%20image/Products.jpg" height="450">

#### CUSTOMER
The chart shows SP, Brazil as the top state with a total order value of 7,546,092, followed by RJ, MG with values ​​of 2,744,633.48 and 2,309,697.32. The top sales with a payment value of > 1 million are located in Brazil, then belong to the Barinas state of Venezuela and South Carolina in the US with a value of 788505.45 and 778,699.09, respectively. The customers with the highest number of purchases are also from the Brazilian states, which corresponds to the above statement about order value distribution. Customer locations are varied in South America, especially Brazil, Argentina, Colombia, Venuzuela, few states in United States, Spain in Europe and Cameroon in Africa. These show that the company has a lot of potential to grow in many horizons.

However, when looking at the customer return rate, 93.82% are only one-time purchase, 6.07% are 2-4 times purchase and only 0.1% are 10 times and above. The statistics present a significant data that needs to be improved. Relatively, when looking at customer recency rate that shows recent visit, 60.35% are more than 6 months that not yet returned, 20.86% are within 6 mnths, 13.13% within 3 months and only 5.66% are within 1 month. These numbers require high attention to in website design, promotion campaigns, price strategy, etc. to improve customer retention.

<img src="https://github.com/Tann1901/e-commerce/blob/main/GIt%20ecommerce%20image/Customers.jpg" height="450">

#### SERVICES
The services offered presented in 99,441 cities with 113,969 product sold. With payment services, one time payment accounted for 49.78%, 2-5 time payments took 28.39%, 5-10 times took 15.57% and the rest was 10-20 or more than 20 times. 

As of delivery services, the time from purchase to shipping to customers will mostly be about 2 weeks with 38.5%, 1 week, etc. However, there are still 4.49% of orders with more than 60 days of delivery. Correlated with the 1-star rating, we can see that the delivery time from 30-60 days has a very high 1-star rate (53.91%), > 60 days will lead to 59.46%. The unavailable order belongs to the electronics industry, this requests a detect and working with delivery service.

With all orders up to then, 97,81% was delivered successfully, 1.11% was shipped, 1.11% was canceled and other tiny amounts were either invoiced, processing, unavailable or approved.
<img src="https://github.com/Tann1901/e-commerce/blob/main/GIt%20ecommerce%20image/Services.jpg" height="450">

#### OVERALL
From August 2017 to now, the business situation has developed and grown steadily. Average revenue is from 1-1.2M per month. We can see that the company was growing fast and had a stable development focusing in low-medium-price products while high value products took very little amount of sales. Customer prefered credit card for payment and settled payments usually from 1-5 times. Delivered time took usually from 0-15 days; however, there were 4.49% products requiring more than 60 days of delivery. 

#### RECOMMENDATION
Customers who bought more than 6 months ago accounted for the highest rate - 60%. we need to look at these customers and ask the customer service department to investigate to find the cause.

Focus on developing products with low and medium price segments, because customers in these two segments account for a large proportion. High value items will come with higher shipping costs and slower payback periods (longer payment installments)

Focus on developing the market and implementing marketing campaigns in South America to create a loyal customer network in this region.

Minimize Cash in payment to ensure safety in transportation. Focus more on one-time payments or online payments to ensure a return on investment.

Shipping services can be improved (cooperating with more shipping services, adding transit warehouse for items with high transit time) thereby helping to improve delivery time to increase customer satisfaction.
