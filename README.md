# DB-Assignment-
**01 = Product: Represents individual items or goods that are sold or managed within the system. Each product has various attributes such as name, description, price, quantity, etc.
Product_Category: Represents a grouping or classification of products based on certain criteria or characteristics. Categories help in organizing products into logical groups for easier management and navigation.
Relationship Type:

The relationship between the "Product" and "Product_Category" entities is typically a one-to-many relationship. This means that one product can belong to only one category, but a category can contain multiple products.
Foreign Key:

In a relational database model, the "Product_Category" entity usually has a primary key (e.g., Category_ID), and the "Product" entity has a foreign key (e.g., Category_ID) that references the primary key of the "Product_Category" entity.
This foreign key establishes the relationship between the two entities. Each product record contains a reference to the category it belongs to.
Usage:

The relationship allows for efficient organization, searching, and filtering of products based on categories. For example, in an e-commerce platform, customers can browse products by navigating through different categories like electronics, clothing, books, etc.
It enables businesses to analyze sales, inventory, and other metrics at both the product and category levels. This helps in making informed decisions regarding product assortment, pricing, and marketing strategies.
Maintenance:

When adding or updating products, the relationship ensures that each product is associated with a valid category.
Changes in category structure or attributes may require updates across related products to maintain data integrity.


**02 = Foreign Key Constraint:

Use a foreign key constraint in the "Product" table that references the primary key of the "Product_Category" table. This ensures that every value in the "Category_ID" (or equivalent) column of the "Product" table corresponds to a valid category in the "Product_Category" table.
When defining the foreign key constraint, ensure that it is set to enforce referential integrity, meaning that any attempt to insert or update a product with a category that does not exist in the "Product_Category" table will be rejected.
Database Triggers:

Implement database triggers that execute before or after insert or update operations on the "Product" table. These triggers can check whether the category assigned to a product exists in the "Product_Category" table.
If the assigned category is invalid, the trigger can raise an error or perform some corrective action, such as assigning a default category or logging the discrepancy for manual review.
Application-Level Validation:

Implement validation logic within the application layer that inserts or updates products in the database.
Before committing changes to the database, verify that the category assigned to each product exists in the "Product_Category" table.
If an invalid category is detected, prevent the transaction from proceeding and notify the user or administrator about the issue.
Stored Procedures:

Use stored procedures to encapsulate the logic for inserting or updating products in the database.

