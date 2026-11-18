StockWise – Inventory Management and Replenishment System

A Database Development Project Using Oracle Database, PL/SQL and Oracle APEX

1. Project Information

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

2. About the Project

StockWise is an inventory management system designed for small retail businesses. The project focuses on helping business owners manage their products, purchases, sales and available stock in one system.

In many small shops, inventory is managed using notebooks or spreadsheets. This can make it difficult to know which products are running out, how much stock is available and when new products should be purchased.

StockWise aims to improve this process by providing a centralized system for managing inventory activities, monitoring stock levels and keeping accurate business records.

3. Problem Statement

Manual inventory management can create several challenges for small retail businesses, including:

Difficulty tracking available product quantities.

Delays in identifying products that are running out.

Errors when recording purchases and sales.

Poor organization of supplier and product information.

Difficulty preparing inventory and sales reports.

StockWise is proposed to address these challenges through a computerized inventory management system.

4. Project Objectives

The main objectives of StockWise are to:

Make it easier to register and manage products and categories.

Maintain records of suppliers, purchases and sales.

Monitor available stock quantities.

Identify products that need restocking.

Reduce errors caused by manual inventory records.

Generate useful inventory, purchase and sales reports.

5. Main Features

The system will provide the following features:

Product Management: Register, update and manage products.

Category Management: Organize products into different categories.

Supplier Management: Register and manage supplier information.

Purchase Management: Record product purchases and received quantities.

Sales Management: Record product sales.

Stock Monitoring: Monitor available product quantities.

Low-Stock Identification: Identify products that need replenishment.

Reporting: View inventory, purchase and sales reports.

6. Database Development

Oracle Database will be used to store and manage the system's information. SQL and PL/SQL will handle database operations and business rules.

The project will apply the following PL/SQL concepts:

PL/SQL Concept

Purpose

Procedures

Record purchases and sales.

Functions

Calculate stock quantities and inventory value.

Triggers

Automatically update stock when transactions occur.

Cursors

Retrieve and process inventory information.

Packages

Organize related PL/SQL operations.

Exception Handling

Handle errors and invalid transactions.

Scheduled Jobs

Check products with low stock.

7. User Interface

Oracle APEX will be used to develop the application interface.

Users will be able to access different sections of the system through a dashboard, forms and reports. The interface will provide a simple way to manage inventory activities without requiring users to write SQL commands.

8. Proposed Database Tables

The initial database design includes the following tables:

PRODUCTS

CATEGORIES

SUPPLIERS

PURCHASES

PURCHASE_DETAILS

SALES

SALES_DETAILS

The database structure may change as the project develops.

9. Data Source

The project will use retail sales and inventory information from publicly available datasets.

Proposed data source: Retail Transactions and Stocks Dataset – Mendeley Data.

Additional sample records may be created for information not included in the dataset, such as supplier details and purchase transactions.

10. Project Development Phases

Phase 0 – Research and Project Proposal

Phase 0 focused on selecting the project topic and preparing the initial project proposal.

The main activities included:

Selecting StockWise as the project topic.

Identifying inventory management challenges faced by small retail businesses.

Defining the problem statement.

Establishing the project objectives.

Identifying the main system features.

Selecting the proposed technologies.

Identifying the initial database tables.

Proposing a suitable data source.

Expected outcome: A clear project proposal describing the purpose, objectives, features, technologies and initial database structure of StockWise.

Phase I – Business Process Modeling

Selected Business Process: Inventory Monitoring and Replenishment Process.

This phase focuses on understanding and modeling how StockWise monitors product quantities and supports the process of replenishing products when stock becomes low.

Business Process Description

The process starts when StockWise retrieves the available product quantities and compares them with the minimum stock levels.

When a product reaches or falls below its minimum stock level, the system generates a low-stock alert. The shop manager reviews the alert and decides whether to approve replenishment.

If approved, inventory staff prepares a purchase order and sends it to the supplier. The supplier delivers the products, and inventory staff checks the delivered items before recording the purchase and updating the available stock.

Actors Involved

Actor

Responsibility

StockWise System

Checks stock quantities and generates low-stock alerts.

Shop Manager

Reviews alerts and approves or rejects replenishment requests.

Inventory Staff

Prepares purchase orders, checks deliveries and records purchases.

Supplier

Receives purchase orders and delivers products.

Database Operations

The process identifies the following data operations:

CREATE: Generate alerts, prepare purchase orders and record purchases.

READ: Retrieve product quantities and minimum stock levels.

UPDATE: Update product stock quantities and relevant records.

Business Process Diagram

Diagram Tool: draw.io

Published Activity Diagram: View StockWise Activity Diagram

Business Process Explanation: View Business Process Explanation PDF

Business Process Diagram PDF: View Business Process Diagram PDF

Expected outcome: A clear representation of the inventory monitoring and replenishment process, showing the actors, activities, decisions and information flow.

Phase II – Database Design and Development

This phase will focus on designing and implementing the Oracle database.

Planned activities include:

Designing the database structure.

Creating the required database tables.

Defining primary keys and foreign keys.

Establishing relationships between tables.

Inserting sample data.

Testing database operations.

Phase III – PL/SQL Development and Application Implementation

This phase will focus on implementing the database business logic and developing the application interface.

Planned activities include:

Developing PL/SQL procedures and functions.

Creating triggers for automatic stock updates.

Implementing cursors and packages.

Applying exception handling.

Creating scheduled jobs for low-stock checks.

Developing the application interface using Oracle APEX.

Testing the main system operations.

11. Project Folder Structure

The project documentation is organized as follows:

Egide_28873_StockWise/
│
├── README.md
│
└── docs/
    └── business_process/
        ├── business_process_diagram.pdf
        └── business_process_explanation.pdf

12. Project Status

Current Stage: Phase I – Business Process Modeling

Phase 0 (Research and Project Proposal) has been completed.

Phase I focuses on modeling the Inventory Monitoring and Replenishment Process and documenting its actors, activities, decisions and information flow.

The next stages will focus on Oracle database design, PL/SQL development and implementation of the application interface using Oracle APEX.

Project: StockWise – Inventory Management and Replenishment System

Student: Egide Niyonzima

Student ID: 28873

Institution: Adventist University of Central Africa (AUCA)
