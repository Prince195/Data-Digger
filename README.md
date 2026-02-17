# Data-Digger

## 📚 Theory – Concepts Used in DATA_DIGGER_DB

This project is based on **Relational Database Management System (RDBMS)** concepts. Below is the detailed theoretical explanation of each concept used in this project.

---

### 🔹 1. Database

A **database** is an organized collection of structured data stored electronically.
In this project, the database `DATA_DIGGER_DB` is created to store information related to:

* Customers
* Orders
* Products
* Order Details

👉 Purpose:
To manage business data efficiently and avoid redundancy.

```sql
CREATE DATABASE DATA_DIGGER_DB;
```

---

### 🔹 2. Tables

A **table** stores data in rows and columns. Each table represents a real-world entity:

* `CUSTOMERS` → Customer information
* `ORDERS` → Orders placed by customers
* `PRODUCTS` → Products available
* `ORDERDETAILS` → Mapping between orders and products

👉 This follows **Entity Relationship (ER Model)** concepts.

---

### 🔹 3. Primary Key

A **Primary Key (PK)** uniquely identifies each record in a table.
It ensures:

* No duplicate values
* No NULL values
* Unique identification of rows

Example:

```sql
CustomerID INT PRIMARY KEY
```

Used in:

* CUSTOMERS.CustomerID
* ORDERS.OrderID
* PRODUCTS.ProductID
* ORDERDETAILS.OrderDetailID

---

### 🔹 4. Foreign Key

A **Foreign Key (FK)** is used to create a relationship between two tables.
It enforces **referential integrity**, meaning related records must exist.

Example:

```sql
FOREIGN KEY (CustomerID) REFERENCES CUSTOMERS(CustomerID)
```

Relations in this project:

* One Customer → Many Orders
* One Order → Many OrderDetails
* One Product → Many OrderDetails

👉 This avoids orphan records.

---

### 🔹 5. Data Types

Different **SQL data types** are used to store appropriate values:

| Data Type     | Use Case                     |
| ------------- | ---------------------------- |
| INT           | IDs, Quantity, Stock         |
| VARCHAR       | Name, Email, Address         |
| DATE          | OrderDate                    |
| DECIMAL(10,2) | Price, TotalAmount, SubTotal |

👉 Choosing correct data types improves **performance and storage efficiency**.

---

### 🔹 6. CRUD Operations

CRUD stands for:

| Operation | SQL Command | Purpose              |
| --------- | ----------- | -------------------- |
| Create    | INSERT      | Add new records      |
| Read      | SELECT      | Fetch records        |
| Update    | UPDATE      | Modify existing data |
| Delete    | DELETE      | Remove records       |

Example:

```sql
INSERT INTO CUSTOMERS VALUES (1, 'Alice', 'alice@gmail.com', 'Ahmedabad');
```

👉 CRUD is the backbone of any database application.

---

### 🔹 7. Constraints

Constraints maintain **data accuracy and consistency**.

| Constraint  | Purpose                             |
| ----------- | ----------------------------------- |
| PRIMARY KEY | Unique row identification           |
| FOREIGN KEY | Maintain table relationships        |
| UNIQUE      | Prevent duplicate values            |
| NOT NULL    | Prevent empty values (can be added) |

Example:

```sql
Email VARCHAR(50) UNIQUE
```

---

### 🔹 8. Aggregate Functions

Aggregate functions perform calculations on multiple rows:

| Function | Description     |
| -------- | --------------- |
| SUM()    | Total of values |
| AVG()    | Average value   |
| MAX()    | Highest value   |
| MIN()    | Lowest value    |

Example:

```sql
SELECT MAX(TotalAmount), MIN(TotalAmount), AVG(TotalAmount) FROM ORDERS;
```

👉 Used for **business analytics**.

---

### 🔹 9. Filtering Data (WHERE Clause)

The `WHERE` clause is used to filter records based on conditions.

Example:

```sql
SELECT * FROM PRODUCTS WHERE Price BETWEEN 500 AND 2000;
```

👉 Helps in retrieving meaningful data.

---

### 🔹 10. Sorting Data (ORDER BY)

The `ORDER BY` clause sorts records in ascending or descending order.

Example:

```sql
SELECT * FROM PRODUCTS ORDER BY Price DESC;
```

---

### 🔹 11. Grouping Data (GROUP BY)

`GROUP BY` groups rows to apply aggregate functions.

Example:

```sql
SELECT ProductID, SUM(Quantity)
FROM ORDERDETAILS
GROUP BY ProductID;
```

👉 Used for reports like **top-selling products**.

---

### 🔹 12. Real-World Use Case

This project simulates an **E-commerce database system**, where:

* Customers place orders
* Orders contain multiple products
* Revenue and sales analysis can be performed

* Inventory systems
* Order management systems
