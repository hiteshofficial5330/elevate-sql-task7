# Elevate Labs - SQL Developer Internship Task 7

## Task Overview
This project is the seventh task for the SQL Developer Internship. [cite_start]The objective is to learn how to create and use SQL Views to simplify complex queries and enhance data security. [cite: 142, 147]

- [cite_start]**Tools Used:** MySQL Workbench [cite: 143]

---
## SQL Script
The `views_script.sql` file is the main deliverable. It contains the SQL code to perform the following:
1.  [cite_start]**Create a View for Simplicity:** A `CustomerSpending` view is created to abstract a complex query that joins `Customers` and `Orders` and calculates total spending per customer. [cite: 146]
2.  [cite_start]**Create a View for Security:** A `PublicProductInfo` view is created to expose only non-sensitive product information (name and price) while hiding confidential data like stock quantity. [cite: 147]
3.  **Usage Examples:** The script includes examples of how to query these views just like regular tables.
4.  **Drop a View:** The script demonstrates how to delete a view.

---
## Interview Questions & Answers

### 1. What is a view?
[cite_start]A view is a virtual table based on the result-set of a stored `SELECT` query. [cite: 151] It contains rows and columns, just like a real table, but it doesn't store the data itself.

### 2. Can we update data through a view?
Sometimes. [cite_start]You can update data through a view only if the view is "updatable." [cite: 152] This generally means the view must be based on a single table and cannot contain aggregate functions (`SUM`, `COUNT`), `GROUP BY`, `DISTINCT`, or `JOIN`s.

### 3. What is a materialized view?
[cite_start]Unlike a regular view, a materialized view is a database object that stores the results of its query physically. [cite: 153] It's a snapshot of the data at a certain point in time and needs to be refreshed periodically. Materialized views are used to improve performance for very complex queries.

### 4. Difference between view and table?
A **table** physically stores data on the disk. [cite_start]A **view** is a stored query that generates its data dynamically when it is accessed; it does not store any data itself (with the exception of materialized views). [cite: 154]

### 5. How to drop a view?
[cite_start]You can delete a view using the `DROP VIEW` command, followed by the view's name: `DROP VIEW view_name;`. [cite: 155]

### 6. Why use views?
[cite_start]Views are used for several reasons: [cite: 156]
-   [cite_start]**Simplicity:** They can hide the complexity of a query involving multiple joins. [cite: 146]
-   [cite_start]**Security:** They can be used to restrict access to specific rows or columns of a table, showing users only the data they are permitted to see. [cite: 147, 158]
-   **Consistency:** They provide a consistent structure for data, even if the underlying tables change.

### 7. Can we create indexed views?
[cite_start]Yes, in some database systems like SQL Server, you can create a unique clustered index on a view. [cite: 157] This makes it a "materialized" or "indexed" view, which can dramatically improve the performance of queries that use it.

### 8. How to secure data using views?
You can create a view that only selects specific, non-sensitive columns from a base table. Then, you grant users permission to access the view instead of the underlying table. [cite_start]This way, they can't see the restricted columns. [cite: 158]

### 9. What are limitations of views?
[cite_start]Key limitations include: they are not always updatable, performance can be slow if the underlying query is very complex, and you generally cannot pass parameters to a view. [cite: 159]

### 10. How does WITH CHECK OPTION work?
`WITH CHECK OPTION` is a constraint that can be added to an updatable view. It enforces that all `INSERT` and `UPDATE` statements executed against the view must result in rows that are visible through that view's `WHERE` clause. [cite_start]It prevents a user from updating a row in a way that would make it disappear from the view. [cite: 160]
