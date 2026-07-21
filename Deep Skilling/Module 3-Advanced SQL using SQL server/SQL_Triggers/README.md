# Employee Management System - SQL Server Triggers

## Objective

The objective of this experiment is to understand and implement different types of SQL Server Triggers. Triggers automatically execute SQL statements when specific database events such as INSERT, UPDATE, DELETE, or LOGON occur.

---

## Software Used

- Microsoft SQL Server
- SQL Server Management Studio (SSMS)

---

## Database Tables

- Departments
- Employees
- EmployeeChanges

---

## Exercises Performed

### Exercise 1
Created an AFTER UPDATE trigger to log salary changes into the EmployeeChanges table.

### Exercise 2
Created an INSTEAD OF DELETE trigger to prevent deletion of employee records.

### Exercise 3
Created a LOGON trigger to restrict database login during maintenance hours.

### Exercise 4
Modified the AFTER UPDATE trigger using ALTER TRIGGER.

### Exercise 5
Deleted an existing trigger using DROP TRIGGER.

### Exercise 6
Created a trigger to automatically update the AnnualSalary column whenever Salary is updated.

---

## SQL Concepts Covered

- AFTER Trigger
- INSTEAD OF Trigger
- LOGON Trigger
- ALTER TRIGGER
- DROP TRIGGER
- inserted and deleted tables
- Trigger Events
- Automatic Data Updates

---

## Advantages of Triggers

- Automates database operations.
- Maintains data integrity.
- Tracks data modifications.
- Prevents unauthorized actions.
- Enforces business rules.

---

## Expected Output

- Salary changes are logged automatically.
- Employee deletions are prevented.
- Database login can be restricted during maintenance.
- Annual salary updates automatically after salary modification.
- Existing triggers can be modified and deleted.

---

## Result

Successfully implemented AFTER, INSTEAD OF, and LOGON triggers, modified existing triggers, deleted triggers, and automated salary calculations using SQL Server Triggers.

---

## Learning Outcomes

After completing this experiment, I learned:

- How to create SQL Server Triggers.
- Difference between AFTER and INSTEAD OF Triggers.
- How LOGON Triggers work.
- How to modify and delete triggers.
- How triggers automate database operations.
- How to use inserted and deleted pseudo tables.

---

## Author

**Name:** Jyothirmai Chapala

**Course:** Cognizant Deepskilling Nurture 5.0

**Technology:** Microsoft SQL Server (SSMS)
