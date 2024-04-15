---
title: "SQL Commands"
datePublished: Tue Apr 02 2024 10:19:47 GMT+0000 (Coordinated Universal Time)
cuid: clui89i5t000708joez89ad9f
slug: sql-commands
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1712053073196/aed3a970-c707-4220-82a7-50b26507711d.jpeg
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1712053149771/14e65473-cfba-482d-b066-90aad1f13e8c.jpeg
tags: data-science, databases, data-structures

---

* **DDL** – Data Definition Language
    

* **DQL** – Data Query Language
    
* **DML** – Data Manipulation Language
    
* **DCL** – Data Control Language
    
* **TCL** – Transaction Control Language
    

## **1) Data Definition Language**

Data Definition Language actually consists of the SQL commands that can be used to define the database schema. It simply deals with descriptions of the database schema and is used to create and modify the structure of database objects in the database. DDL is a set of SQL commands used to create, modify, and delete database structures but not data. These commands are normally not used by a general user

* **CREATE** \- It is used to create a new Table
    

```sql
 CREATE TABLE TABLE_NAME (COLUMN_NAME DATATYPES[,….]);
```

* **DROP -** It is used to delete tables from the database
    

```sql
DROP TABLE table_name;
```

* **TRUNCATE** \- It is used to delete all the rows and all data.
    

```sql
TRUNCATE TABLE table_name;
```

* **ALTER** \- It is used to alter the structure of the database. To add a new column in the table
    

```sql
ALTER TABLE table_name ADD column_name COLUMN-definition;
```

* **COMMENT** \- Comments are used to explain sections of SQL statements, or to prevent execution of SQL statements.
    

```sql
/*Select all the columns
of all the records
in the Customers table:*/
SELECT * FROM Customers;
```

* **RENAME** \- It is used to alter name of the table
    

```sql
ALTER TABLE table_name
RENAME COLUMN old_name TO new_name;
```

## **2) Data Query Language**

We can define DQL as follows it is a component of SQL statement that allows getting data from the database and imposing order upon it. It includes the SELECT statement. This command allows getting the data out of the database to perform operations with it. When a SELECT is fired against a table or tables the result is compiled into a further temporary table, which is displayed

* **SELECT** \- It is used to select the attribute based on the condition described by the WHERE clause.
    

```sql
SELECT emp_name FROM employee WHERE age > 20;
```

## **3) Data Manipulation Language**

It is the component of the SQL statement that controls access to data and to the database. Basically, DCL statements are grouped with DML statements.

* **INSERT** \- It is used to insert data into the row of a table.
    

```sql
INSERT INTO TABLE_NAME(col1, col2, col3,…. col N)
VALUES (value1, value2, value3, …. valueN);
```

* **UPDATE** \- It is used to update the data in the row of a table.
    

```sql
UPDATE table_name SET [column_name1= value1,…column_nameN = valueN]
[WHERE CONDITION]
```

* **DELETE** \- It is used to remove one or more rows from a table
    

```sql
DELETE - It is used to remove one or more rows from a table
DELETE FROM table_name [WHERE condition];
```

## 4) Data Control Language

DCL commands are used to grant and take back authority from any database user.

**GRANT -** It is used to give user access privileges to a database.

```sql
GRANT SELECT, UPDATE ON MY_TABLE TO SOME_USER, ANOTHER_USER;
```

**REVOKE** \- It is used to take back permissions from the user.

```sql
REVOKE SELECT, UPDATE ON MY_TABLE FROM USER1, USER2;
```

## 5) Transaction Control Language

TCL commands can only use with DML commands like INSERT, DELETE and UPDATE only.

**COMMIT -** Commit command is used to save all the steps in the query.

```sql
COMMIT;
```

**ROLLBACK -** Rollback command is used to undo transactions that have not already been saved to the database.

```sql
ROLLBACK;
```

**SAVEPOINT-** It is used to roll the transaction back to a certain point without rolling back the entire transaction.

```sql
SAVEPOINT SAVEPOINT_NAME;
```