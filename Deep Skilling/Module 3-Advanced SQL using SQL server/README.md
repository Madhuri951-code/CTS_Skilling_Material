# SQL Indexes - Online Retail Store

## Objective

The objective of this experiment is to understand the concept of SQL indexes and how they improve database query performance. Different types of indexes such as Non-Clustered Index, Clustered Index, and Composite Index are implemented using Microsoft SQL Server.

---

## Software Used

- Microsoft SQL Server 2025
- SQL Server Management Studio (SSMS)

---

## Problem Statement

An online retail store contains customer, product, order, and order details information. As the database grows, searching records becomes slower. SQL indexes are used to improve the speed of data retrieval.

---

## Database Tables

The following tables are created:

- Customers
- Products
- Orders
- OrderDetails

These tables are related using Primary Keys and Foreign Keys.

---

## Exercises Performed

### Exercise 1: Non-Clustered Index

**Objective:**
Create a non-clustered index on the `ProductName` column.

**Operations:**
- Query product details before index creation.
- Create a Non-Clustered Index.
- Query product details after index creation.
- Compare query performance.

---

### Exercise 2: Clustered Index

**Objective:**
Understand Clustered Indexes and create an index on the `OrderDate` column.

**Note:**
In SQL Server, the Primary Key automatically creates a Clustered Index by default. Therefore, a Non-Clustered Index is created on `OrderDate` for demonstration purposes.

**Operations:**
- Query order details before index creation.
- Create index on `OrderDate`.
- Query order details after index creation.

---

### Exercise 3: Composite Index

**Objective:**
Create a Composite Index on `CustomerID` and `OrderDate`.

**Operations:**
- Query orders using multiple conditions.
- Create Composite Index.
- Execute the same query after index creation.
- Observe improved query performance.

---

## SQL Concepts Covered

- Primary Key
- Foreign Key
- Clustered Index
- Non-Clustered Index
- Composite Index
- Query Optimization
- Index Performance
- Database Design

---

## Types of Indexes

### Clustered Index
- Stores data physically in sorted order.
- Only one clustered index can exist per table.
- Created automatically on the Primary Key (by default).

### Non-Clustered Index
- Stores index separately from table data.
- Multiple non-clustered indexes can be created.
- Improves search performance.

### Composite Index
- Index created using two or more columns.
- Improves queries that filter on multiple columns.

---

## Advantages of Indexes

- Faster data retrieval.
- Improves SELECT query performance.
- Reduces table scanning.
- Optimizes database operations.
- Useful for large databases.

---

## Limitations of Indexes

- Increases storage space.
- Slightly slows INSERT, UPDATE, and DELETE operations.
- Too many indexes can reduce write performance.

---

## Expected Output

- Product search becomes faster after creating a Non-Clustered Index.
- Order search improves after indexing the `OrderDate` column.
- Composite Index improves queries using both `CustomerID` and `OrderDate`.
- Successfully display created indexes using SQL Server system catalog.

---

## Result

Successfully created and tested Non-Clustered Index, Composite Index, and studied Clustered Index concepts using Microsoft SQL Server (SSMS). The experiment demonstrated how indexes improve query performance and optimize database searches.

---



---

