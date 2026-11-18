StockWise – Database Normalization

1. Introduction

Database normalization is the process of organizing data into related tables to reduce duplication and improve data consistency.

For the StockWise Inventory Management and Replenishment System, normalization is applied to the raw dataset stockwise_raw_dataset.csv.

The dataset contains:

600 transaction records

20 columns

384 sales records

216 purchase records

The normalization process is explained using UNF, 1NF, 2NF and 3NF.

Note: The sample records below are taken from the generated CSV dataset.

2. Unnormalized Form (UNF)

Unnormalized Form is the original raw dataset before separating information into related database tables.

The original dataset contains transaction, product, category, supplier and customer information in the same table.

Problems with UNF

Supplier information is repeated across transactions.

Product information is repeated when a product appears in multiple transactions.

Category information is repeated.

Customer information is repeated in sales records.

Sale and purchase records use different transaction ID fields.

Sample UNF records

TransactionID

Type

ProductID

ProductName

CategoryName

SupplierName

CustomerID

Quantity

T0001

SALE

31

Bread Loaf - Pack 2

Bakery

FreshMart Suppliers

53

22

T0002

SALE

39

Cola Drink 500ml - Pack 3

Beverages

East Africa Distributors

48

12

T0003

SALE

17

Frozen Chips 1kg

Frozen Foods

FrostLine Distributors

23

32

T0004

SALE

14

Exercise Book

Stationery

City Paper Products

19

21

T0005

SALE

16

Floor Cleaner 1L

Cleaning

QuickClean Supplies

4

30

These are selected columns from the original raw records. The complete raw dataset has 20 columns.

3. First Normal Form (1NF)

A table is in First Normal Form when:

Each column contains atomic (single) values.

Each record is unique.

There are no repeating groups in a single cell.

The StockWise raw CSV already has one product per transaction record and individual values in its columns. Therefore, its records satisfy the basic 1NF requirements.

Sample 1NF records

TransactionID

TransactionType

TransactionDate

ProductID

ProductName

Quantity

UnitPrice

T0001

SALE

2026-05-14

31

Bread Loaf - Pack 2

22

877

T0002

SALE

2026-07-14

39

Cola Drink 500ml - Pack 3

12

753

T0003

SALE

2026-09-02

17

Frozen Chips 1kg

32

3295

T0004

SALE

2026-07-03

14

Exercise Book

21

696

T0005

SALE

2026-04-07

16

Floor Cleaner 1L

30

2516

Result: Each transaction has individual values, and each row represents one product transaction.

4. Second Normal Form (2NF)

A table is in Second Normal Form when:

It is already in 1NF.

Every non-key attribute depends on the whole primary key, not only part of a composite key.

For the StockWise logical design, transaction header information is separated from transaction product details.

This separation allows one sale or purchase to contain multiple products in the database design.

A. SALES table

SaleID (PK)

SaleDate

CustomerID (FK)

S0001

2026-05-14

53

S0002

2026-07-14

48

S0003

2026-09-02

23

S0004

2026-07-03

19

S0005

2026-04-07

4

B. SALES_DETAILS table

SaleID (PK, FK)

ProductID (PK, FK)

Quantity

S0001

31

22

S0002

39

12

S0003

17

32

S0004

14

21

S0005

16

30

The primary key of SALES_DETAILS is a composite key made from SaleID and ProductID.

C. PURCHASES table

PurchaseID (PK)

SupplierID (FK)

PurchaseDate

P0006

7

2026-11-17

P0009

6

2026-05-05

P0011

3

2026-01-26

P0012

3

2026-03-29

P0014

8

2026-06-19

D. PURCHASE_DETAILS table

PurchaseID (PK, FK)

ProductID (PK, FK)

Quantity

UnitCost

P0006

15

14

112

P0009

24

11

1092

P0011

3

26

423

P0012

21

9

421

P0014

20

25

1207

Result: Transaction header information is separated from product quantities and purchase costs. This supports transactions containing multiple products.

5. Third Normal Form (3NF)

A table is in Third Normal Form when:

It is already in 2NF.

Non-key attributes depend on the primary key.

Non-key attributes do not depend on other non-key attributes.

In StockWise, category, supplier and customer information are separated into their own tables to reduce repeated information.

A. CATEGORIES table

CategoryID (PK)

CategoryName

7

Bakery

1

Beverages

10

Frozen Foods

8

Stationery

9

Cleaning

B. SUPPLIERS table

SupplierID (PK)

SupplierName

SupplierCity

2

FreshMart Suppliers

Kigali

3

East Africa Distributors

Nairobi

12

FrostLine Distributors

Kigali

7

City Paper Products

Kigali

10

QuickClean Supplies

Kigali

C. CUSTOMERS table

CustomerID (PK)

CustomerName

CustomerCity

53

Customer 053

Rubavu

48

Customer 048

Huye

23

Customer 023

Rubavu

19

Customer 019

Kigali

4

Customer 004

Kigali

D. PRODUCTS table

ProductID (PK)

ProductName

CategoryID (FK)

SupplierID (FK)

UnitPrice

CurrentStock

MinimumStock

31

Bread Loaf - Pack 2

7

2

877

125

13

39

Cola Drink 500ml - Pack 3

1

3

753

159

26

17

Frozen Chips 1kg

10

12

3295

54

19

14

Exercise Book

8

7

696

98

14

16

Floor Cleaner 1L

9

10

2516

82

13

The remaining tables are SALES, SALES_DETAILS, PURCHASES and PURCHASE_DETAILS, as shown in the 2NF section.

Result: Each category, supplier and customer is stored separately. Products reference categories and suppliers using foreign keys.

6. Final Normalized Database Tables

The final StockWise database design contains eight tables:

CATEGORIES

SUPPLIERS

CUSTOMERS

PRODUCTS

SALES

SALES_DETAILS

PURCHASES

PURCHASE_DETAILS

Main relationships

One category can have many products.

One supplier can supply many products.

One supplier can have many purchases.

One customer can make many sales.

One sale can contain many sale details.

One product can appear in many sale details.

One purchase can contain many purchase details.

One product can appear in many purchase details.

7. Conclusion

Normalization helps organize the StockWise database into related tables. It reduces repeated information, improves data consistency and makes it easier to manage products, suppliers, customers, sales and purchases.

The final logical design uses eight related tables with primary keys and foreign keys to maintain relationships between records.
