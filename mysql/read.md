________________________________________________________________
### Interview Questions for MySQL: 
#### 0: How to get the current MySQL version?
To get the current MySQL version, you can use the following methods:

Command Line (Linux/Unix): Use the command `mysql --version`.
Command Line (Windows): Use the command `mysql -V`.
MySQL Client: Log in to the MySQL client and run the SQL query `SELECT VERSION();`
phpMyAdmin: The MySQL version is typically displayed on the initial page
MySQL Workbench: You can find the MySQL version in the "Server Status" section.

#### 1: What is the MySQL server’s default port?
The default port for MySQL server is 3306.

#### 2: How many different tables are present in MySQL?
The number of different tables in a MySQL database can vary widely and depends on the specific database schema and the data model used. There is no fixed or standard number of tables in MySQL. The number of tables is determined by the design and requirements of the database. Some databases may have just a few tables, while others can have many tables to represent different data entities and relationships.

#### 3: What is Difference between CHAR_LENGTH and LENGTH?
`CHAR_LENGTH` counts the number of characters, while `LENGTH` counts the number of bytes in a string.


#### 4: What do you understand by % and _ in the like statement?
`%` matches any sequence of characters (including zero).
`_` matches any single character.

#### 5: How many index columns can be created in a table?
There's no strict limit; you can create multiple indexes on a table, but be cautious of performance implications.

#### 6: What are string types available for columns?
Common string types include VARCHAR, CHAR, TEXT, and ENUM.


#### 7: Explain the main difference between FLOAT and DOUBLE?
FLOAT is a single-precision floating-point number, while DOUBLE is a double-precision floating-point number. DOUBLE provides higher precision but uses more storage.

#### 8: Explain the difference between having and where clause in MySQL.
- `WHERE` filters rows before aggregation.
- `HAVING` filters results after aggregation.

#### 9: How can we add a column in MySQL?
Use the `ALTER TABLE` statement with the `ADD COLUMN` clause to add a new column to an existing table.

 
#### 10: How to delete columns in MySQL?
Use the `ALTER TABLE` statement with the `DROP COLUMN` clause to delete a column from an existing table.


#### 11: How to delete a table in MySQL?
Use the `DROP TABLE` statement followed by the table name to delete a table in MySQL.


#### 12: How to get the top 10 rows?
Use the `SELECT` statement with `LIMIT 10` to retrieve the top 10 rows from a table.


#### 13: What is the use of the ‘DISTINCT’ keyword in MySQL?
The `DISTINCT` keyword is used to retrieve unique values from a column in a table. It ensures that only distinct values are returned, eliminating duplicates.

#### 14: Which storage engines are used in MySQL?
Common storage engines in MySQL include InnoDB, MyISAM, and MEMORY. Each engine has unique features and is suitable for different use cases.

#### 15: How to create a table in MySQL?
Use the `CREATE TABLE` statement to define the table structure, specify column names and data types, and set constraints like primary keys and foreign keys.


#### 16: What types of relationships are used in MySQL?
Common types include one-to-one, one-to-many, and many-to-many relationships. These are established using keys like primary and foreign keys.


#### 17: How to insert Date in MySQL? 
You can insert a date into a MySQL table using the `INSERT` statement with a valid date format, like `YYYY-MM-DD`.


#### 18: What is join? Tell different join in MySQL.
A join is used to combine rows from two or more tables based on a related column between them. Common joins include INNER JOIN, LEFT JOIN (or LEFT OUTER JOIN), RIGHT JOIN (or RIGHT OUTER JOIN), and FULL JOIN (or FULL OUTER JOIN).


#### 19: What is a primary key? How to drop the primary key in MySQL? 
A primary key is a unique identifier for each record in a table. To drop a primary key, use the `ALTER TABLE` statement with the `DROP PRIMARY KEY` clause.


#### 20: What is InnoDB?
InnoDB is a popular storage engine in MySQL known for its support of transactions, foreign keys, and ACID compliance. It's widely used for reliable and transaction-safe database operations.


#### 21: What is the difference between UNION and UNION ALL in MySQL?
- `UNION` removes duplicate rows.
- `UNION ALL` includes all rows, even duplicates

#### 22: What is a `timestamp` in MySQL?
A `timestamp` in MySQL is a data type used to store date and time values with a time zone.

#### 23: What is the use of ENUMs in MySQL?
ENUMs are used to represent a set of predefined values for a column. They help ensure data consistency and limit possible values.


#### 24: How can you control max size of heap in MySQL?
You can set the max heap size using the `--max-heap-table-size` and `--tmp-table-size` parameters in your MySQL configuration.

#### 25: What is a view? How to create a view? 
A view is a virtual table created from the result of a SQL query. To create a view, use the `CREATE VIEW` statement, specifying the query defining the view.

#### 26: Where MyISAM table will be stored and also give MyISAM formats of storage?
MyISAM tables are stored in the database directory as separate files. Common MyISAM storage formats include .MYD (data), .MYI (index), and .frm (table format) files.

#### 27:  How can we save images in MySQL?
Images can be saved in MySQL by storing them in a BLOB (Binary Large Object) column. BLOBs can store binary data, such as images, as part of a table's record.

#### 28: What are trigger and how many TRIGGERS are available in MySQL table?
Triggers are database objects that automatically perform actions in response to predefined events. In MySQL, you can create AFTER INSERT, AFTER UPDATE, and AFTER DELETE triggers for tables.

#### 29: What are Access Control Lists?
Access Control Lists (ACLs) are lists of permissions that specify which users or system processes are granted access to objects, as well as what operations are allowed on given objects in a system.

#### 30: What are various ways to create an index?
You can create indexes using CREATE INDEX statements, by defining primary keys, or by using the ALTER TABLE statement. Common index types are B-tree, hash, and full-text indexes.


#### 31: What are a clustered index and a non clustered index?
In MySQL, the concept of a clustered index is mainly associated with the InnoDB storage engine. A clustered index determines the physical order of rows in a table and is typically based on the primary key. A non-clustered index doesn't affect the physical order of rows and is separate from the data.


#### 32: How to validate emails using a single query?
You can validate emails using regular expressions in a query. For example, `SELECT email FROM users WHERE email REGEXP '^[A-Za-z0-9._%+-]+@[A-Za-z0-9.-]+\\.[A-Za-z]{2,4}$'`;

#### 33: How can you handle the –secure-file-priv in MySQL?
You can set the `--secure-file-priv` option in the MySQL configuration file to specify a directory where MySQL can write secure files for data import/export operations.

#### 34:  How do you create a database in MySQL?
Use the `CREATE DATABASE` statement to create a new database in MySQL.

#### 35: How do you create a table using MySQL?
Use the `CREATE TABLE` statement to define and create a new table in a MySQL database. Specify the table's structure, column names, data types, and constraints.


#### 36: What is BLOB in MySQL?
BLOB stands for Binary Large Object. It's a MySQL data type used to store binary data, such as images, audio, or other non-text data.


#### 37: How to add users in MySQL?
You can add users in MySQL using the `CREATE USER` statement or through a client application. You need to specify their username and password.


#### 38: What are MySQL Triggers?
MySQL triggers are database objects that automatically execute actions (e.g., SQL statements) in response to specific events, such as INSERT, UPDATE, or DELETE operations on a table.

#### 39: How many Triggers are possible in MySQL?
In MySQL, you can create multiple triggers for each table. The number of triggers you can create is not strictly limited, but it's good practice to keep them manageable for clarity and maintainability.

#### 40: What is the MySQL server?
The MySQL server is the core component of the MySQL database management system. It handles database operations, such as querying, updating, and managing data.


#### 41: What are the MySQL clients and utilities?
MySQL provides various client applications and utilities like the command-line client, MySQL Workbench, phpMyAdmin, and others. These tools allow you to interact with and manage MySQL databases.


#### 42: Can you explain the logical architecture of MySQL?
The logical architecture of MySQL includes components like the Query Optimizer, Storage Engines, and the SQL Layer. The Query Optimizer optimizes queries, the Storage Engines handle data storage and retrieval, and the SQL Layer manages SQL parsing and execution.


#### 43: What is Scaling in MySQL?
Scaling in MySQL refers to the process of increasing the capacity and performance of a MySQL database system to handle growing workloads and user demands. It can involve techniques like sharding, replication, and clustering to distribute and manage data across multiple servers.

#### 44: What is the purpose of the SHOW TABLES command in MySQL?
The SHOW TABLES command is used to list the tables in the current database.

#### 45: What is normalization and denormalization in the context of database design?
Normalization is the process of organizing data in a database to reduce redundancy and improve data integrity. Denormalization is the opposite, where data is intentionally duplicated to optimize query performance.


#### 46: What is the ACID properties in the context of database transactions?
ACID stands for `Atomicity, Consistency, Isolation, and Durability`. These properties ensure that database transactions are reliable, and data remains consistent even in the face of errors.

#### 47: How can you prevent SQL injection in MySQL?
To prevent SQL injection, use parameterized queries or prepared statements. These techniques ensure that user inputs are treated as data and not executable SQL code.


#### 48: What is the difference between a LEFT JOIN and a RIGHT JOIN in MySQL?
A LEFT JOIN retrieves all records from the left table and matching records from the right table, while a RIGHT JOIN retrieves all records from the right table and matching records from the left table.


#### 49: What is a stored procedure in MySQL?
A stored procedure is a set of SQL statements that can be executed as a single unit. It is stored in the database and can be called multiple times with different parameters.

#### 50: How do you export data from a MySQL table to a CSV file?
You can export data to a CSV file using the `SELECT...INTO OUTFILE` statement or by using MySQL client utilities like `mysqldump` with the `--tab` option.
