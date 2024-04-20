---
title: "SQL SERVER – Checking If a Column Exists in a Table"
datePublished: Sat Apr 20 2024 15:23:53 GMT+0000 (Coordinated Universal Time)
cuid: clv891wt0000508l1avqofl4x
slug: sql-server-checking-if-a-column-exists-in-a-table
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1713626583409/f7f63cc0-3032-4824-aef5-25e3bd5dc466.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1713626623688/d16b093b-b6e9-487b-a671-13a73b0eebde.png
tags: data, data-science, databases, data-structures, sql

---

One of the common tasks that developers deal with when working on database-related projects is ensuring that certain columns exist in a table. This task is particularly relevant when you’re working on scripts to modify the structure of a table, such as adding new columns, and you want to avoid errors caused by attempting to add an existing column. Let us see a script that will help check if a Column Exists in a Table.

### Using INFORMATION\_SCHEMA.COLUMNS

The INFORMATION\_SCHEMA.COLUMNS view can be used to verify the existence of a column. The INFORMATION\_SCHEMA views provide access to database metadata, including information about columns in all tables in the database.

```sql
IF EXISTS(SELECT *
FROM INFORMATION_SCHEMA.COLUMNS
WHERE TABLE_NAME = 'myTableName'
AND COLUMN_NAME = 'myColumnName')
BEGIN
-- Column Exists
END
```

In this example, a SELECT query is constructed to find a row in INFORMATION\_SCHEMA.COLUMNS that match the specified table and column name. If such a row exists, the column exists in the table.

### Using sys.columns

Another approach is to use the sys.columns view, which also provides metadata about columns in tables.

```sql
IF EXISTS(SELECT 1 FROM sys.columns
WHERE Name = N'columnName'
AND Object_ID = Object_ID(N'schemaName.tableName'))
BEGIN
-- Column Exists
END
```

In this case, the Object\_ID function is used to get the ID of the table, and this is compared with the object\_id column in sys.columns.

### Using COL\_LENGTH

You can also use the COL\_LENGTH function, which returns the length of a specified column. If the column does not exist, COL\_LENGTH returns NULL.

```sql
IF COL_LENGTH('schemaName.tableName', 'columnName') IS NOT NULL
BEGIN
-- Column Exists
END
```

One advantage of this approach is that COL\_LENGTH only returns data about committed changes, irrespective of the isolation level.

### Wrapping Up

Each method has its advantages, and the best one to use depends on your specific circumstances. The INFORMATION\_SCHEMA.COLUMNS and sys.columns views provide a wealth of information about columns, while the COL\_LENGTH function can be faster since it uses cached database metadata.