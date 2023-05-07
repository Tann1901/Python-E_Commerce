# e-commerce
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

The sales experienced an improvement throughout the year, reaching total of .... in 2017 and ... in 2018. However, there should be more attention paid in improving customer satifaction and ....

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


### 1.  Introduction

The analysis performs the business overall of X-ecommerce company that was established in the end of 2016 up to 2018 with details of services, products, customer and sales overview. 

This report will also include the reccommendations for their performance.

### 2. Question
<img src="https://github.com/Tann1901/e-commerce/blob/main/GIt%20ecommerce%20image/1.%20X-ecommerce%20question%20graph-Map%201.png" height="250">
### 3. Data Understanding
#### a. Entity
<img src="https://github.com/Tann1901/e-commerce/blob/main/GIt%20ecommerce%20image/2.%20Entity.jpg" height="250">
#### b. Attribute
<img src="https://github.com/Tann1901/e-commerce/blob/main/GIt%20ecommerce%20image/3.%20Attribute.jpg" height="250">
#### c. Entity Diagram
<img src="https://github.com/Tann1901/e-commerce/blob/main/GIt%20ecommerce%20image/4.%20Entity%20diagram.jpg" height="250">


#### d. Data Cleaning
1. Create dataframe
<img src="https://github.com/Tann1901/e-commerce/blob/main/GIt%20ecommerce%20image/5.%20Create%20dataframe.jpg" height="250">
2. Check if dataframe is null
<img src="https://github.com/Tann1901/e-commerce/blob/main/GIt%20ecommerce%20image/6.%20Check%20null.jpg" height="250">
3. Combine all related table to find null and duplicated values
<img src="https://github.com/Tann1901/e-commerce/blob/main/GIt%20ecommerce%20image/8.%20Check%20null%20value%20of%20combined%20table.jpg" height="250">
4. Result of null values
<img src="https://github.com/Tann1901/e-commerce/blob/main/GIt%20ecommerce%20image/9.%20Check%20duplicated%20value.jpg" height="250">
5. Check if null values can be removed
<img src="https://github.com/Tann1901/e-commerce/blob/main/GIt%20ecommerce%20image/10.%20check%20order_id%20null%20and%20not%20null.jpg" height="250">
6. Remove null
<img src="https://github.com/Tann1901/e-commerce/blob/main/GIt%20ecommerce%20image/11.%20find%20%25%20differences%20of%20removing%20null%20value.jpg" height="250">
7. Check if non-English category names can be removed
8. Remove null
9. Update data after cleaning

### 4. Analyze Method
Python, PowerBi, MySQL, Canva

### 5. Analyzation
SALES
In general, the total revenue reached 17.79 million, with freight accounted for 2.28 million and goods sold was 15.51 million. Due to the payment types were varied with payment installmentment, there was still 2.58 million receivable amount. Total order count reached 97191 and total customer records reached 99441. 
The sales were increasing throughout the year with peak recorded in November, 2017 at 1,575,685.79. In the latest year - 2018, the sales revenues were more stable throughout the months in the range of 1.2 - 1.5 million.  Closely look at payment type, 76.84% were credit card, 19,92% was cash and a small portion of debit and voucher. The review score charts also showed 56.19%, 18.89%, 8.45%, 3.54% and 12.93% prespectively from 5-1. These numbers presented the overall sales records with further details analyzed below.

PRODUCT
The graph shows highest proportion product group revenue are: health_beauty, bed_bath_table, watch_gifts, computers_accessories, sport_leisure ranging from 7.06%-8.76%. These belong to low average price group and and with average payment settlement at 2-4 times. Average delivery fee for these items are in range of $16-18.9.
In contrast, the highest average prices belong to the group computers, small_appliances_home_oven_and_coffee, home_appliances_2, agro_industry_and_commerce. These group also come with high freight and payment installment times with average from 3-6 imstallment period. These categories also fell in low selling rate at below 1% while delivery fee is in range $36-48. 

CUSTOMER
The chart shows SP, Brazil as the top state with a total order value of 7,546,092, followed by RJ, MG with values ​​of 2,744,633.48 and 2,309,697.32. The top sales with a payment value of > 1 million are located in Brazil, then belong to the Barinas state of Venezuela and South Carolina in the US with a value of 788505.45 and 778,699.09, respectively. The customers with the highest number of purchases are also from the Brazilian states, which corresponds to the above statement about order value distribution. Customer locations are varied in South America, especially Brazil, Argentina, Colombia, Venuzuela, few states in United States, Spain in Europe and Cameroon in Africa. These show that the company has a lot of potential to grow in many horizons.

However, when looking at the customer return rate, 93.82% are only one-time purchase, 6.07% are 2-4 times purchase and only 0.1% are 10 times and above. The statistics present a significant data that needs to be improved. Relatively, when looking at customer recency rate that shows recent visit, 60.35% are more than 6 months that not yet returned, 20.86% are within 6 mnths, 13.13% within 3 months and only 5.66% are within 1 month. These numbers require high attention to in website design, promotion campaigns, price strategy, etc. to improve customer retention.


SERVICES
The services offered presented in 99,441 cities with 113,969 product sold. With payment services, one time payment accounted for 49.78%, 2-5 time payments took 28.39%, 5-10 times took 15.57% and the rest was 10-20 or more than 20 times. 

As of delivery services, the time from purchase to shipping to customers will mostly be about 2 weeks with 38.5%, 1 week, etc. However, there are still 4.49% of orders with more than 60 days of delivery. Correlated with the 1-star rating, we can see that the delivery time from 30-60 days has a very high 1-star rate (53.91%), > 60 days will lead to 59.46%. The unavailable order belongs to the electronics industry, this requests a detect and working with delivery service.

With all orders up to then, 97,81% was delivered successfully, 1.11% was shipped, 1.11% was canceled and other tiny amounts were either invoiced, processing, unavailable or approved.

OVERALL
From August 2017 to now, the business situation has developed and grown steadily. Average revenue is from 1-1.2M per month. We can see that the company was growing fast and had a stable development focusing in low-medium-price products while high value products took very little amount of sales. Customer prefered credit card for payment and settled payments usually from 1-5 times. Delivered time took usually from 0-15 days; however, there were 4.49% products requiring more than 60 days of delivery. 

RECOMMENDATION
Customers who bought more than 6 months ago accounted for the highest rate - 60%. we need to look at these customers and ask the customer service department to investigate to find the cause.
Focus on developing products with low and medium price segments, because customers in these two segments account for a large proportion. High value items will come with higher shipping costs and slower payback periods (longer payment installments)
Focus on developing the market and implementing marketing campaigns in South America to create a loyal customer network in this region.
Minimize Cash in payment to ensure safety in transportation. Focus more on one-time payments or online payments to ensure a return on investment.
Shipping services can be improved (cooperating with more shipping services, adding transit warehouse for items with high transit time) thereby helping to improve delivery time to increase customer satisfaction.
