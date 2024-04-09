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

---

In addition to Data Definition Language (DDL) and Data Manipulation Language (DML), there is another category of SQL commands known as Data Control Language (DCL). DCL statements are used to control access to data within the database, including permissions and security settings.

### Data Control Language (DCL)

DCL statements are responsible for managing user access rights and permissions within a database. These statements are used to grant or revoke privileges to users and roles.

Common DCL statements include:

1. **GRANT**: Used to provide specific privileges to a user or a role.
   ```sql
   GRANT SELECT, INSERT, UPDATE ON Employees TO user1;
   ```

2. **REVOKE**: Used to revoke previously granted privileges from a user or a role.
   ```sql
   REVOKE INSERT ON Employees FROM user1;
   ```

DCL statements are essential for maintaining data security and controlling who can access, modify, or delete data within a database. By using GRANT and REVOKE statements, database administrators can ensure that only authorized users have appropriate access to the database objects and operations.

### Example of DCL Usage

```sql
-- Grant SELECT permission on Employees table to user1
GRANT SELECT ON Employees TO user1;

-- Revoke INSERT permission on Employees table from user2
REVOKE INSERT ON Employees FROM user2;
```

In summary, DCL statements complement DDL and DML by providing tools for managing database security and access control. Together, these SQL commands form the foundation for creating and maintaining secure and well-managed database systems. Understanding and using DCL statements is crucial for database administrators to enforce data security policies and ensure the integrity and confidentiality of sensitive information.

---

Apart from Data Definition Language (DDL), Data Manipulation Language (DML), and Data Control Language (DCL), another category of SQL commands is Transaction Control Language (TCL). TCL statements are used to manage transactions within a database, ensuring data consistency and integrity.

### Transaction Control Language (TCL)

TCL statements are used to control the transactions in a database. A transaction is a sequence of operations performed as a single logical unit of work. TCL statements help manage these transactions by specifying the beginning and ending of transactions and controlling their behavior.

Common TCL statements include:

1. **COMMIT**: This statement is used to permanently save the changes made by a transaction to the database.
   ```sql
   COMMIT;
   ```

2. **ROLLBACK**: This statement is used to undo the changes made by a transaction that has not been committed yet, restoring the database to its previous state.
   ```sql
   ROLLBACK;
   ```

3. **SAVEPOINT**: This statement sets a named point within a transaction to which you can later roll back.
   ```sql
   SAVEPOINT sp1;
   ```

4. **SET TRANSACTION**: This statement sets properties for the current transaction.
   ```sql
   SET TRANSACTION ISOLATION LEVEL READ COMMITTED;
   ```

TCL statements are essential for maintaining the integrity of database transactions. They allow developers to control when changes made by a transaction are made permanent (by committing) or discarded (by rolling back). Using TCL statements appropriately ensures that database operations are executed reliably and consistently, even in the event of errors or unexpected conditions.

### Example of TCL Usage

```sql
-- Start a new transaction
BEGIN;

-- Perform some DML operations
INSERT INTO Employees (emp_id, emp_name) VALUES (1, 'John Doe');
UPDATE Employees SET emp_department_id = 101 WHERE emp_id = 1;

-- Check if everything is correct
-- If satisfied, commit the transaction to make changes permanent
COMMIT;

-- If not satisfied or encountering errors, rollback the transaction
ROLLBACK;
```

In summary, TCL statements play a crucial role in managing database transactions, ensuring that data modifications are applied correctly and consistently. Understanding and utilizing TCL statements is important for database developers and administrators to maintain data integrity and reliability in transactional database systems.
