StockWise – Data Dictionary

Student Name: Egide Niyonzima
Student ID: 28873
Course: INSY 8311 – Database Development with PL/SQL
Project: StockWise – Inventory Management and Replenishment System

1. Introduction

A data dictionary describes the tables and columns used in a database. It explains what each column stores and identifies the primary keys and foreign keys.

The StockWise data dictionary is based on the logical database design prepared during normalization.

2. Database Tables

The StockWise database contains eight main tables:

CATEGORIES

SUPPLIERS

CUSTOMERS

PRODUCTS

SALES

SALES_DETAILS

PURCHASES

PURCHASE_DETAILS

3. Table Descriptions

3.1 CATEGORIES

This table stores the different categories of products in the shop.

Column

Description

Key

Required

CategoryID

Unique identification for each category

PK

Yes

CategoryName

Name of the category

—

Yes

3.2 SUPPLIERS

This table stores information about suppliers who provide products to the shop.

Column

Description

Key

Required

SupplierID

Unique identification for each supplier

PK

Yes

SupplierName

Name of the supplier

—

Yes

SupplierCity

City where the supplier is located

—

No

3.3 CUSTOMERS

This table stores information about customers who buy products.

Column

Description

Key

Required

CustomerID

Unique identification for each customer

PK

Yes

CustomerName

Name of the customer

—

Yes

CustomerCity

City where the customer lives

—

No

3.4 PRODUCTS

This table stores information about products available in the shop.

Column

Description

Key

Required

ProductID

Unique identification for each product

PK

Yes

ProductName

Name of the product

—

Yes

CategoryID

Category to which the product belongs

FK

Yes

SupplierID

Main supplier of the product

FK

Yes

UnitPrice

Selling price of one product

—

Yes

CurrentStock

Available quantity of the product

—

Yes

MinimumStock

Minimum quantity allowed before a restock alert

—

Yes

3.5 SALES

This table stores general information about sales transactions.

Column

Description

Key

Required

SaleID

Unique identification for each sale

PK

Yes

SaleDate

Date when the sale was made

—

Yes

CustomerID

Customer who made the purchase

FK

Yes

3.6 SALES_DETAILS

This table stores the individual products included in each sale.

Column

Description

Key

Required

SaleID

Identifies the related sale

PK, FK

Yes

ProductID

Identifies the product sold

PK, FK

Yes

Quantity

Number of product units sold

—

Yes

Note: SaleID and ProductID together form a composite primary key.

3.7 PURCHASES

This table stores information about products purchased from suppliers.

Column

Description

Key

Required

PurchaseID

Unique identification for each purchase

PK

Yes

SupplierID

Supplier providing the products

FK

Yes

PurchaseDate

Date when the purchase was made

—

Yes

3.8 PURCHASE_DETAILS

This table stores the products and quantities included in each purchase.

Column

Description

Key

Required

PurchaseID

Identifies the related purchase

PK, FK

Yes

ProductID

Identifies the purchased product

PK, FK

Yes

Quantity

Number of product units purchased

—

Yes

UnitCost

Cost of one purchased unit

—

Yes

Note: PurchaseID and ProductID together form a composite primary key.

4. Relationships Between Tables

Parent Table

Child Table

Relationship

CATEGORIES

PRODUCTS

One-to-Many

SUPPLIERS

PRODUCTS

One-to-Many

CUSTOMERS

SALES

One-to-Many

SALES

SALES_DETAILS

One-to-Many

PRODUCTS

SALES_DETAILS

One-to-Many

SUPPLIERS

PURCHASES

One-to-Many

PURCHASES

PURCHASE_DETAILS

One-to-Many

PRODUCTS

PURCHASE_DETAILS

One-to-Many

5. Primary Key and Foreign Key Explanation

Primary Key (PK): A primary key uniquely identifies each record in a table. For example, ProductID identifies each product.

Foreign Key (FK): A foreign key connects one table to another. For example, CategoryID in the PRODUCTS table refers to CategoryID in the CATEGORIES table.

Composite Primary Key: A key made from two or more columns. In SALES_DETAILS, SaleID and ProductID are used together to identify each sales line.

6. Business Rules

Each product must belong to one category.

Each product must have one main supplier.

A category can contain many products.

A supplier can supply many products.

A customer can make many sales.

A sale can contain several products.

A purchase must be associated with a supplier.

A purchase can contain several products.

Product quantity must not be negative.

MinimumStock determines when a product needs replenishment.

7. Conclusion

The StockWise data dictionary explains the purpose of each table and column in the database. It also shows how primary keys and foreign keys connect the tables.

This document will guide the creation of the database tables in Oracle during the implementation phase.
