StockWise – Dataset Card

1. Dataset Information

Item

Description

Dataset Name

StockWise Raw Dataset

Project Name

StockWise – Inventory Management and Replenishment System

Student Name

Egide Niyonzima

Student ID

28873

Course

Database Development with PL/SQL

Dataset File

stockwise_raw_dataset.csv

File Format

CSV

Number of Records

600

Number of Columns

20

Date Prepared

18 November 2026

Source

Synthetically generated for this academic project

Licence

Original synthetic academic dataset; no external dataset licence applies

2. Dataset Description

The StockWise Raw Dataset contains sample inventory and transaction information prepared for the development of an Inventory Management and Replenishment System.

It represents a shop that manages products, categories, suppliers, customers, sales and purchases.

The dataset contains 600 transaction records:

384 sales records.

216 purchase records.

Each record represents one product transaction.

3. Main Data Fields

The dataset contains information about:

Transaction identification and transaction type.

Transaction dates.

Product identification and product names.

Product categories.

Supplier information.

Customer information.

Product quantities.

Selling prices and purchase costs.

Current stock and minimum stock levels.

4. Intended Use

The dataset will be used to:

Practice database normalization from UNF to 3NF.

Identify entities and relationships.

Design an Entity Relationship Diagram (ERD).

Create a data dictionary.

Map raw dataset fields into normalized database tables.

Support the development of the StockWise inventory management system.

5. Data Quality Checks

The following checks will be performed before loading the dataset into the database.

Quality Check

Purpose

Missing values

Identify empty or missing important fields.

Duplicate records

Check whether transaction records are repeated.

Data types

Ensure dates, numbers and text use appropriate formats.

Primary keys

Check that transaction and entity identifiers are valid.

Foreign keys

Check that related product, supplier, customer and category IDs exist.

Invalid quantities

Identify zero or negative transaction quantities.

Invalid prices

Identify negative or incorrect prices.

Transaction types

Confirm that records are classified as SALE or PURCHASE.

Validation status: These are the planned quality checks. Their results must be recorded after running the checks on the CSV file.

6. Privacy and Limitations

The dataset is synthetically generated.

It does not represent actual customers or real business transactions.

Customer and supplier details are sample information.

The dataset is intended for academic learning and system development.

Its values may not represent real market prices or actual stock conditions.

7. Conclusion

The StockWise Raw Dataset provides sample information for designing and developing the StockWise Inventory Management and Replenishment System.

It will be used to demonstrate database normalization, logical database design and data management using Oracle Database and PL/SQL.
