## Anomaly Analysis

Insert Anomaly

In the flat dataset (orders_flat.csv), order information and customer information are stored in the same table. For example, rows like order_id = ORD2001 contain customer_id, order_date, status and total_amount together. If we want to add a new customer who has not placed any order yet, we cannot insert that customer because the table requires order information. This is an insert anomaly.

Update Anomaly

In the flat dataset, customer information is repeated across multiple rows. For example, the same customer_id such as CUST048 appears in multiple orders like ORD2011, ORD2014, ORD2069, and ORD2070. If we need to update the information for this customer, we would need to update multiple rows. If one row is missed, the database will contain inconsistent data. This is an update anomaly.

Delete Anomaly

If we delete a row representing an order, we may also lose important information about that customer or transaction. For example, if the only order for a customer such as order_id = ORD2006 is deleted, the information about customer CUST008 might be lost from the dataset. This is a delete anomaly.

## Normalization Justification

Keeping all order, customer, product, and sales representative information in a single table may look simpler at first, but it causes several problems. In the flat dataset, customer information and order information are mixed together, which leads to repeated data across many rows.

For example, the same customer_id appears in multiple orders, which means the same customer data is stored repeatedly. If any information about that customer changes, such as contact details or location, it must be updated in many rows. This increases the chance of mistakes and inconsistent data.

By normalizing the dataset into separate tables such as customers, products, orders, order_items, and sales_reps, each entity is stored only once. Relationships between them are maintained using foreign keys. This reduces redundancy, improves data consistency, and makes the database easier to maintain. Therefore, normalization is necessary for maintaining a clean and reliable database structure.