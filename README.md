StockWise – Inventory Management and Replenishment System

Project Information

Detail

Information

Student Name

Egide Niyonzima

Student ID

28873

University

Adventist University of Central Africa (AUCA)

Course

Database Development with PL/SQL (INSY 8311)

Database

Oracle Database

Programming Language

SQL and PL/SQL

User Interface

Oracle APEX

About the Project

StockWise is an inventory management system designed for small retail businesses. The project focuses on helping business owners keep track of their products, purchases, sales and available stock.

In many small shops, inventory is managed using notebooks or spreadsheets. This can make it difficult to know which products are running out, how much stock is available and when new products should be purchased.

StockWise aims to make this process easier by bringing inventory operations into one system.

Project Objectives

The main objectives of StockWise are to:

Make it easier to manage products and categories.

Keep records of suppliers, purchases and sales.

Monitor available stock quantities.

Identify products that need restocking.

Reduce errors caused by manual inventory records.

Provide useful inventory, purchase and sales reports.

Main Features

The system will allow users to:

Register and manage products.

Organize products into categories.

Register suppliers.

Record product purchases.

Record product sales.

Monitor available stock.

Identify products that need restocking.

View inventory, purchase and sales reports.

Database Development

Oracle Database will be used to store and manage the system's information. PL/SQL will handle the main operations and business rules.

The project will include:

Procedures: For recording purchases and sales.

Functions: For calculating stock quantities and inventory value.

Triggers: For updating stock automatically.

Cursors: For retrieving inventory information.

Packages: For organizing PL/SQL operations.

Exception Handling: For handling invalid transactions.

Scheduled Jobs: For checking low-stock products.

User Interface

Oracle APEX will be used to develop the application interface.

Users will be able to access different sections of the system through a dashboard, forms and reports without having to write SQL commands.

Proposed Database Tables

The initial database design includes:

PRODUCTS

CATEGORIES

SUPPLIERS

PURCHASES

PURCHASE_DETAILS

SALES

SALES_DETAILS

The database structure may change as the project develops.

Data Source

The project will use retail sales and inventory information from publicly available datasets.

Proposed source: Retail Transactions and Stocks Dataset – Mendeley Data.

Additional sample records may be created for information not included in the dataset, such as supplier details and purchase transactions.

Project Phases

Phase 0 – Research and Project Proposal

This phase focused on selecting the project topic, identifying the business problem, defining the project objectives and proposing the main system features and database tables.

Phase I – Business Process Modeling

Selected Business Process: Inventory Monitoring and Replenishment Process.

This process explains how StockWise monitors product quantities, identifies low-stock products and supports the replenishment process.

The process involves four main actors:

StockWise System: Checks stock quantities and generates low-stock alerts.

Shop Manager: Reviews alerts and approves or rejects replenishment requests.

Inventory Staff: Prepares purchase orders, checks deliveries and records purchases.

Supplier: Receives purchase orders and delivers products.

The process also identifies important database operations, including creating records, retrieving information and updating stock quantities.

Diagram Tool: draw.io

Published Business Process Diagram:
View StockWise Activity Diagram

Business Process Explanation:
View Business Process Explanation PDF

Diagram PDF:
View Business Process Diagram PDF

Phase II – Database Design and Development

This phase will focus on designing and implementing the Oracle database, creating the required tables, defining relationships and inserting sample data.

Phase III – PL/SQL Development and Application Implementation

This phase will focus on implementing PL/SQL procedures, functions, triggers, cursors, packages and exception handling, together with developing the user interface using Oracle APEX.

Project Folder Structure

StockWise/
│
├── README.md
│
└── docs/
    └── business_process/
        ├── business_process_diagram.pdf
        └── business_process_explanation.pdf

Project Status

Current stage: Phase I – Business Process Modeling.

Phase 0 (Research and Project Proposal) has been completed. Phase I focuses on modeling the Inventory Monitoring and Replenishment Process and documenting the activities, actors and information flow.

The next stages will focus on database design, PL/SQL development and the Oracle APEX application interface.
