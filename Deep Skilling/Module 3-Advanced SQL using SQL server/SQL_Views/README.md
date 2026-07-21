# Employee Management System - SQL Views

## Objective

The objective of this experiment is to understand the concept of SQL Views and how they simplify complex queries by presenting data in a virtual table format. The experiment also demonstrates the use of computed columns within views.

---

## Software Used

- Microsoft SQL Server
- SQL Server Management Studio (SSMS)

---

## Database Tables

- Departments
- Employees

---

## Exercises Performed

### Exercise 1 - Simple View

Created a view named `vw_EmployeeBasicInfo` to display employee details along with department names by joining Employees and Departments tables.

---

### Exercise 2 - Computed Column (Full Name)

Created a view named `vw_EmployeeFullName` that generates a computed column `FullName` by combining FirstName and LastName.

---

### Exercise 3 - Computed Column (Annual Salary)

Created a view named `vw_EmployeeAnnualSalary` to calculate annual salary using:

AnnualSalary = Salary × 12

---

### Exercise 4 - Employee Report

Created a comprehensive report view named `vw_EmployeeReport` containing:

- Employee ID
- Full Name
- Department Name
- Annual Salary
- Bonus (10% of Annual Salary)

---

## Concepts Covered

- SQL Views
- Simple View
- Join View
- Computed Columns
- String Concatenation
- Arithmetic Expressions
- Virtual Tables
- Data Abstraction

---

## Advantages of Views

- Simplifies complex SQL queries.
- Provides data security by hiding sensitive columns.
- Improves code reusability.
- Makes reporting easier.
- Presents data in a user-friendly format.

---

## Expected Output

- Display employee information using views.
- Generate Full Name using computed columns.
- Calculate Annual Salary.
- Calculate Bonus automatically.
- Generate a complete employee report.

---

## Result

Successfully created SQL Views with computed columns and generated employee reports using Microsoft SQL Server.

---


