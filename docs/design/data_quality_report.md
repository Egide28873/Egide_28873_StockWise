StockWise – Data Quality Report

1. Introduction

This report presents the data quality checks performed on the StockWise raw dataset.

The dataset is named stockwise_raw_dataset.csv. It contains inventory, sales and purchase transaction information used for the StockWise Inventory Management and Replenishment System.

2. Dataset Overview

Description

Result

Total records

600

Total columns

20

Sales records

384

Purchase records

216

Unique transaction IDs

600

Unique products

40

Unique categories

10

Unique suppliers

12

Unique customers

60

Earliest transaction date

2026-01-01

Latest transaction date

2026-11-17

3. Missing Values Check

Missing values were checked in all 20 columns.

Some missing values are expected because sales and purchases contain different information.

Column

Missing values

Explanation

TransactionID

0

All records have transaction IDs.

TransactionType

0

All records have transaction types.

TransactionDate

0

All records have dates.

SaleID

216

Purchase records do not have SaleID.

PurchaseID

384

Sales records do not have PurchaseID.

CustomerID

216

Purchase records do not require customers.

CustomerName

216

Purchase records do not require customers.

CustomerCity

216

Purchase records do not require customers.

Other columns

0

No missing values found.

Result: No unexpected missing values were found.

4. Duplicate Records Check

The dataset was checked for duplicate records and transaction identifiers.

Check

Result

Duplicate complete records

0

Duplicate TransactionID values

0

Duplicate SaleID values

0

Duplicate PurchaseID values

0

Result: No duplicate records or transaction identifiers were found.

5. Data Type and Validity Checks

The following checks were performed:

Check

Invalid records found

Invalid transaction dates

0

Invalid transaction types

0

Zero or negative quantities

0

Negative unit prices

0

Negative unit costs

0

Negative current stock

0

Negative minimum stock

0

The transaction dates use the YYYY-MM-DD format.

The transaction types are SALE and PURCHASE.

Result: All checked values passed the basic validity checks.

6. Relationship and Consistency Checks

The dataset was checked to ensure that related identifiers consistently refer to the same information.

Relationship

Result

ProductID to ProductName

Consistent

ProductID to CategoryID

Consistent

ProductID to SupplierID

Consistent

CategoryID to CategoryName

Consistent

SupplierID to SupplierName

Consistent

SupplierID to SupplierCity

Consistent

CustomerID to CustomerName

Consistent

CustomerID to CustomerCity

Consistent

The following transaction rules were also checked:

All sales have a SaleID and CustomerID.

All purchases have a PurchaseID.

Sales do not have PurchaseID values.

Purchases do not have SaleID values.

Purchase records do not contain customer information.

Result: All the above consistency checks passed.

7. Summary of Results

Quality area

Result

Missing values

Passed – only expected missing values

Duplicate records

Passed

Transaction identifiers

Passed

Data types and dates

Passed

Quantities and prices

Passed

Relationship consistency

Passed

Transaction classification

Passed

8. Limitations

Although the dataset passed the checks above, it has some limitations:

It is synthetically generated and does not represent real business transactions.

It contains sample customer and supplier information.

It represents only a limited number of products and categories.

Current stock and minimum stock values are sample inventory information.

Further validation will be required when loading the data into Oracle Database.

9. Conclusion

The StockWise raw dataset contains 600 records and 20 columns. The data quality checks found no duplicate records, invalid dates, negative quantities or prices, or inconsistent identifier relationships.

The missing values found in SaleID, PurchaseID and customer fields are expected because sales and purchase transactions require different information.

The dataset is suitable for the next stage of academic database design and development, subject to further validation during database loading.
