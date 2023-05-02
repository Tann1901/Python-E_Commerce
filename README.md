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
![](../../../OneDrive/Desktop/GIt%20ecommerce%20image/X-ecommerce%20question%20graph-Map%201.png)
### 3. Data Understanding
#### a. Entity
![](../../../OneDrive/Desktop/GIt%20ecommerce%20image/2.%20Entity.jpg)
#### b. Attribute
![](../../../OneDrive/Desktop/GIt%20ecommerce%20image/3.%20Attribute.jpg)
#### c. Entity Diagram
![](../../../OneDrive/Desktop/GIt%20ecommerce%20image/4.%20Entity%20diagram.jpg)
#### d. Data Cleaning
1. Create dataframe

2. Check if dataframe is null

3. Combine all related table to find null and duplicated value

4. 