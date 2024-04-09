In SQL (Structured Query Language), queries are broadly categorized into two main types based on their purpose and function within a database: Data Definition Language (DDL) and Data Manipulation Language (DML).

### Data Definition Language (DDL)

DDL statements are used to define the structure and schema of a database. These statements are responsible for creating, modifying, and deleting database objects such as tables, indexes, views, and constraints.

Common DDL statements include:

1. **CREATE**: Used to create database objects like tables, views, indexes, or stored procedures.
   ```sql
   CREATE TABLE Employees (
       emp_id INT PRIMARY KEY,
       emp_name VARCHAR(50),
       emp_department_id INT
   );
   ```

2. **ALTER**: Used to modify the structure of an existing database object.
   ```sql
   ALTER TABLE Employees
   ADD emp_salary DECIMAL(10, 2);
   ```

3. **DROP**: Used to delete an existing database object.
   ```sql
   DROP TABLE Employees;
   ```

4. **TRUNCATE**: Used to remove all records from a table without deleting the table structure.
   ```sql
   TRUNCATE TABLE Employees;
   ```

### Data Manipulation Language (DML)

DML statements are used to manage data within database objects. These statements are responsible for querying, inserting, updating, and deleting data records in tables.

Common DML statements include:

1. **SELECT**: Used to retrieve data from one or more tables.
   ```sql
   SELECT emp_name, emp_department_id
   FROM Employees
   WHERE emp_id = 123;
   ```

2. **INSERT**: Used to add new records into a table.
   ```sql
   INSERT INTO Employees (emp_id, emp_name, emp_department_id)
   VALUES (1, 'John Doe', 101);
   ```

3. **UPDATE**: Used to modify existing records in a table.
   ```sql
   UPDATE Employees
   SET emp_department_id = 102
   WHERE emp_id = 1;
   ```

4. **DELETE**: Used to remove records from a table.
   ```sql
   DELETE FROM Employees
   WHERE emp_id = 1;
   ```

DML statements allow manipulation of the actual data stored in the database tables, enabling operations such as inserting new data, updating existing data, or removing unwanted data. These statements are crucial for maintaining the integrity and relevance of the data within a database.

In summary, DDL is focused on defining and managing the structure of database objects, while DML is focused on managing the data stored within those objects. Understanding the differences between these two types of SQL queries is essential for effective database design, development, and management.
