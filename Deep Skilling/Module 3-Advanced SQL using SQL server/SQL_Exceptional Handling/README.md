# Employee Management System - SQL Server Exception Handling

## Objective

The objective of this experiment is to understand exception handling in Microsoft SQL Server using TRY...CATCH, THROW, RAISERROR, transactions, and error logging.

---

## Software Used

- Microsoft SQL Server
- SQL Server Management Studio (SSMS)

---

## Database Tables

- Departments
- Employees
- AuditLog

---

## Exercises Performed

### Exercise 1
Created a stored procedure to insert employee records using TRY...CATCH and log errors into the AuditLog table.

### Exercise 2
Modified the stored procedure to use THROW after logging errors, allowing the application to receive the original exception.

### Exercise 3
Validated employee salary using RAISERROR before inserting records.

### Exercise 4
Implemented nested TRY...CATCH blocks to update an employee's department and handle invalid department errors.

### Exercise 5
Created a transaction-based stored procedure to insert multiple employee records and roll back all changes if any insert failed.

### Exercise 6
Used RAISERROR with different severity levels to generate warnings for low salaries and errors for negative salaries.

---

## SQL Concepts Covered

- TRY...CATCH
- THROW
- RAISERROR
- Transactions
- BEGIN TRANSACTION
- COMMIT
- ROLLBACK
- Stored Procedures
- Error Logging
- Nested TRY...CATCH

---

## Advantages

- Improves application reliability.
- Prevents invalid data entry.
- Maintains transaction consistency.
- Provides detailed error logging.
- Supports custom business rule validation.

---

## Expected Output

- Employee records inserted successfully.
- Duplicate email errors logged in AuditLog.
- Invalid salaries rejected.
- Invalid department transfers logged.
- Failed transactions rolled back.
- Warning and error messages displayed using RAISERROR.

---

## Result

Successfully implemented SQL Server exception handling using TRY...CATCH, THROW, RAISERROR, nested exception handling, and transaction management.

---

