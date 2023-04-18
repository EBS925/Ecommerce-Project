# Ecommerce-Project

Dat512 

Canisius College

Kyle Eberle
# Project Description
In this project I was tasked with using the BigQuery data platform to look into ecommerce data. The specific prompt was as follows,
1. Evaluation of products, analyzing product sales, and product web views, and a justified recommendation on cutting 20% of products from the store, listing the products to remove.
2. Examination of users, users' data, purchase and returns behavior, and web behavior. Delivering a categorization of users into meaningful segments with an explanation of how that categorization could be used by the business. Each user will need to be assigned a category.

# Data source used for project
https://console.cloud.google.com/bigquery?project=arcane-rigging-381423&supportedpurview=project&ws=!1m29!1m4!4m3!1sbigquery-public-data!2sthelook_ecommerce!3sorder_items!1m4!4m3!1sbigquery-public-data!2sthelook_ecommerce!3sevents!1m3!3m2!1sbigquery-public-data!2sthelook_ecommerce!1m4!1m3!1sarcane-rigging-381423!2sbquxjob_2dffe55b_1879196333d!3sUS!1m4!4m3!1sbigquery-public-data!2sthelook_ecommerce!3susers!1m4!1m3!1sarcane-rigging-381423!2sbquxjob_1e0ae68a_18791748108!3sUS

# Project Overview
#### Data Pull/Initial Review
* Data was pulled from the BigQuery public ecommerce data
* The main method of anlysis was done using SQL
* Data was exported out from BigQuery an loaded in to Jupyter Notebooks as panda dataframes
* General select statments were performed on each table to ensure data was captured correctly
#### Prompt Part 1
* There were ~11k unique products in this data set
  * We were asked to look into cutting this list down by the worst selling 
    20% (~2200 unique products)
* I wrote a query to get to the 2200 worst selling products by total item sold, along with price.
  If we had more info on what these specific items were, we could dive into if these 
  are possibly priced too high based on the item in question, or other realted factors
* I then wrote another query that joined the events and order items tables to look into web views by product
  * This showcased the web views which i decided to group by events cart and product, as these reffered tp
    either putting a product in the cart or just viewing the products page
  *From the product sales and web views queries, the products that overlap in both views would be my recommendation 
   for which products to remove from the companies circulation.
    *These products are those that sell the least amount while also being viewed online by users the least amount
#### Prompt Part 2
* This prompt was more focused on looking into the user specific data along with their purchase, return, and web behavoirs 
  * I started out by checking some general info like gender split and country of origin among the users
    * Which came to no major discovery with importance in these variables
* The first larger query i wrote was centered around the users web behavior
  * The main focus was zeroing in on the traffic source that lead the users to the products.
    These sources included by Email, Social Media, Youtube, etc
  * What I can do with the view, seen further in the notebook, is segment the users by traffic source 
    that lead them to the product, and plan on some tactics to keep
    interest from the users high...for example those that frequently visiting based off email
    can be sent target coupons and discounts via email to drive higher sales. Those
    visiting based of social media like facebook and youtube ads, can be identified
    and have trageted ads sent their way
* The second larger query i wrote was centered around the users purchase and cancel behavior
  * The main focus was zeroing in on the event type of what the end result of the product with the user was.
    These events included adding to cart, purchased, and cancelled.
  * This view, further seen in the notebook, shows how often a user puts items in a cart to 
    actually purchasing. With this the company can dive deeper into which products 
    specifically are most often put in the cart then not purchased.
    These items can be given discount events, special advertising, or 
    be removed from circulation if rarely purchased
