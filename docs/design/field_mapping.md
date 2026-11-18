PRODUCTS

ProductID

ProductName

PRODUCTS

ProductName

CategoryID

PRODUCTS

CategoryID (FK)

SupplierID

PRODUCTS

SupplierID (FK)

UnitPrice

PRODUCTS

UnitPrice

CurrentStock

PRODUCTS

CurrentStock

MinimumStock

PRODUCTS

MinimumStock

SaleID

SALES

SaleID

TransactionDate

SALES

SaleDate

CustomerID

SALES

CustomerID (FK)

PurchaseID

PURCHASES

PurchaseID

TransactionDate

PURCHASES

PurchaseDate

SupplierID

PURCHASES

SupplierID (FK)

SaleID

SALES_DETAILS

SaleID (PK, FK)

ProductID

SALES_DETAILS

ProductID (PK, FK)

Quantity

SALES_DETAILS

Quantity

PurchaseID

PURCHASE_DETAILS

PurchaseID (PK, FK)

ProductID

PURCHASE_DETAILS

ProductID (PK, FK)

Quantity

PURCHASE_DETAILS

Quantity

UnitCost

PURCHASE_DETAILS

UnitCost

3. Fields Used During Data Processing

Some raw fields help identify and separate records but are not stored as columns in the final eight tables.

Raw field

How it is used

TransactionID

Identifies a raw transaction record during processing.

TransactionType

Determines whether a record belongs to SALES or PURCHASES.

TransactionDate

Becomes SaleDate or PurchaseDate depending on transaction type.

CategoryName

Used when inserting or checking category records.

SupplierName

Used when inserting or checking supplier records.

CustomerName

Used when inserting or checking customer records.

4. Data Transformation Rules

If TransactionType is SALE, insert the transaction information into SALES and its product information into SALES_DETAILS.

If TransactionType is PURCHASE, insert the transaction information into PURCHASES and its product information into PURCHASE_DETAILS.

Category information is stored in CATEGORIES.

Supplier information is stored in SUPPLIERS.

Customer information is stored in CUSTOMERS.

Product information is stored in PRODUCTS.

Foreign keys connect the related tables.

Repeated category, supplier, customer and product information should be inserted only once, using the corresponding IDs.

5. Example of Mapping One Raw Record

The following is an example from the raw CSV dataset:

Field

Example value

TransactionID

T0001

TransactionType

SALE

TransactionDate

2026-05-14

SaleID

S0001

ProductID

31

ProductName

Bread Loaf - Pack 2

CategoryID

7

CategoryName

Bakery

SupplierID

2

CustomerID

53

Quantity

22

UnitPrice

877

This record is separated into the following tables:

CATEGORIES

CategoryID: 7

CategoryName: Bakery

SUPPLIERS

SupplierID: 2

SupplierName: FreshMart Suppliers

SupplierCity: Kigali

CUSTOMERS

CustomerID: 53

CustomerName: Customer 053

CustomerCity: Rubavu

PRODUCTS

ProductID: 31

ProductName: Bread Loaf - Pack 2

CategoryID: 7

SupplierID: 2

UnitPrice: 877

CurrentStock: 125

MinimumStock: 13

SALES

SaleID: S0001

SaleDate: 2026-05-14

CustomerID: 53

SALES_DETAILS

SaleID: S0001

ProductID: 31

Quantity: 22

The supplier's information is linked to the product through SupplierID. It is not necessary to repeat the supplier's name in the SALES table.

6. Important Data Handling Notes

Blank PurchaseID values in sale records are not inserted into PURCHASES.

Blank SaleID values in purchase records are not inserted into SALES.

Customer information is used for sales records.

Supplier information is used for purchase records and product information.

CurrentStock and MinimumStock are product-level values in this generated dataset. They should not be treated as historical stock balances for each transaction.

UnitCost is stored in PURCHASE_DETAILS according to the proposed logical design.

7. Conclusion

The field mapping shows how the raw transaction dataset is separated into eight related tables. This organization reduces repeated information, improves data consistency and supports the StockWise inventory management and replenishment system.
