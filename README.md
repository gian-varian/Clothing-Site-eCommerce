# Dataset Source
The Look E-Commerce: <br/>
https://console.cloud.google.com/bigquery?ws=!1m4!1m3!3m2!1sbigquery-public-data!2sthelook_ecommerce
# Dataset Summary
The Look is a fictitious eCommerce clothing site developed by the Looker team. The dataset contains information about customers, products, orders, logistics, web events, and digital marketing campaigns. The contents of this dataset are synthetic and provided to industry practitioners for the purpose of product discovery, testing, and evaluation
# Tables & Variables
1. __Table__:<br/>
   users (Represents registered customers) <br/><br/>
   __Variables__: <br/>
   id (Unique user ID) <br/>
   first_name, last_name <br/>
   email, age, gender <br/>
   state, city, country, zip, latitude, longitude <br/>
   traffic_source (How the user found the site) <br/>
   created_at (Account creation timestamp) <br/>

2. __Table__:<br/>
   orders (Represents order placed) <br/><br/>
   __Variables__:<br/>
   order_id (Unique order identifier)
   user_id (Foreign Key to users)
   status (Order status: Complete, Cancelled, Returned, Shipped, Processing)
   gender
   created_at, returned_at, shipped_at, delivered_at
   num_of_item (Number of items in the order)

3. __Table__:<br/>
   order_items (Item detail for each order) <br/><br/>
   __Variables__:<br/>
   id (Unique ordered item ID)
   order_id (Foreign Key to orders)
   user_id (Foreign Key to users)
   product_id (Foreign Key to products)
   inventory_item_id (Foreign Key to inventory_items)
   status (Item-level order status)
   sale_price (Actual price paid)
   created_at, shipped_at, delivered_at, returned_at

4. __Table__:<br/>
   products (The product catalog) <br/><br/>
   __Variables__:<br/>
   id (Unique product ID)
   name (Product name)
   brand
   category (e.g., "Jeans", "Tops & Tees")
   department ("Men" or "Women")
   sku (Unique Code)
   retail_price, cost
   distribution_center_id

5. __Table__:<br/>
   Inventory_items (Physical inventory units (a product can have many inventory items)) <br/><br/>
   __Variables__:<br/><br/>
   id – Unique inventory item ID
   product_id – FK to products
   product_category, product_name, product_brand, product_department
   product_retail_price, cost
   created_at, sold_at
   distribution_center_id

6. distribution_centers
Fulfillment centers.

id
name – e.g., "Memphis TN"
latitude, longitude

7. events
Clickstream / web behavior log.

id – Event ID
user_id – FK to users (nullable for anonymous sessions)
sequence_number – Order of events in session
session_id
created_at
ip_address, city, state, country, zip, latitude, longitude
os, browser
traffic_source
event_type – e.g., "home", "category", "product", "cart", "purchase", "cancel"
uri – Page visited
