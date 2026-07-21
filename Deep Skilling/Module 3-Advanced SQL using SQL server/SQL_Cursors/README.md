# Employee Management System - SQL Server Cursors

## Objective

The objective of this experiment is to understand how SQL Server Cursors work. Cursors allow processing one row at a time instead of processing the entire result set at once.

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

### Exercise 1

Created a cursor to iterate through all employee records and print employee details one by one.

### Exercise 2

Implemented different types of SQL Server cursors:

- Static Cursor
- Dynamic Cursor
- Forward-Only Cursor
- Keyset Cursor

and compared their behavior.

---

## SQL Concepts Covered

- DECLARE CURSOR
- OPEN CURSOR
- FETCH NEXT
- WHILE Loop
- @@FETCH_STATUS
- CLOSE CURSOR
- DEALLOCATE CURSOR
- Static Cursor
- Dynamic Cursor
- Forward-Only Cursor
- Keyset Cursor

---

## Cursor Types

### Static Cursor

Creates a snapshot of the data. Changes made after opening the cursor are not visible.

### Dynamic Cursor

Reflects all changes made to the data while the cursor is open.

### Forward-Only Cursor

Moves only in the forward direction and provides faster performance.

### Keyset Cursor

Allows updates to existing rows but does not show newly inserted rows.

---

## Advantages of Cursors

- Process records one at a time.
- Useful for row-by-row operations.
- Easy to implement business logic for individual records.
- Helpful when sequential processing is required.

---

## Limitations of Cursors

- Slower than set-based queries.
- Consumes more memory.
- Not recommended for large datasets.

---

## Expected Output

- Employee details displayed one by one.
- Successful execution of Static, Dynamic, Forward-Only, and Keyset cursors.

---

## Result

Successfully implemented SQL Server Cursors and understood the behavior of different cursor types.

---

## Learning Outcomes

After completing this experiment, I learned:

- How to create and use SQL Server Cursors.
- How to fetch records one by one.
- Difference between Static, Dynamic, Forward-Only, and Keyset cursors.
- How to open, close, and deallocate cursors.
- When cursors should and should not be used.

---

## Author

**Name:** Gundlakunta Madhuri

**Course:** Cognizant Deepskilling Nurture 5.0

**Technology:** Microsoft SQL Server (SSMS)
