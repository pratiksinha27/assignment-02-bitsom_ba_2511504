## Anomaly Analysis

### Insert Anomaly
In the orders_flat.csv dataset, if we want to add a new product that has not yet been ordered, we cannot insert the product without creating an order entry. This happens because product information is stored together with order details.

Example columns involved:
product_name, order_id

### Update Anomaly
Customer information such as city or name appears multiple times across different rows. If a customer's city changes, it must be updated in multiple rows. If one row is missed, inconsistent data may occur.

Example columns involved:
customer_name, customer_city

### Delete Anomaly
If the only order containing a particular product is deleted, the product information is also lost. This means deleting an order can unintentionally remove important product data.
