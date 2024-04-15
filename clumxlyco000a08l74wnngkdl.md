---
title: "How to Find Duplicates in SQL SERVER: A Step-by-Step Guide"
seoTitle: "Find Duplicate Records in SQL Server - Complete Guide"
seoDescription: "Learn how to identify and remove duplicate records in SQL Server databases using different techniques like GROUP BY, INTERSECT, ROW_NUMBER(), and temporary "
datePublished: Fri Apr 05 2024 17:20:23 GMT+0000 (Coordinated Universal Time)
cuid: clumxlyco000a08l74wnngkdl
slug: how-to-find-duplicates-in-sql-server-a-step-by-step-guide
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1712334827928/56e9310d-1410-43d8-ab7d-c9dd7057aa66.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1712337614828/d2a1d9f9-c733-4962-82bf-db738778fd23.png
tags: data-science, databases, datastructure

---

Hi techies in this article we would see what are the different ways in which we would find duplicates in SQL SERVER

**1) Identify the Columns to Check for Duplicates** The first step is to determine which columns you want to check for duplicates. These are usually the key columns or a combination of columns that should be unique.

2) **Use the** `GROUP BY` Clause with `HAVING` Condition One way to find duplicates is to use the `GROUP BY` clause along with the `HAVING` condition. This approach groups the records by the columns you want to check for duplicates and then filters the groups that have more than one record.

```sql
SELECT column1, column2, ..., COUNT(*) AS Duplicates
FROM YourTableName
GROUP BY column1, column2, ...
HAVING COUNT(*) > 1;
```

**3)Use the** `INTERSECT` Operator Another approach is to use the `INTERSECT` operator to find the intersection of records between the original table and a derived table with distinct values.

```sql
SELECT column1, column2, ...
FROM YourTableName
INTERSECT
SELECT column1, column2, ...
FROM (
  SELECT DISTINCT column1, column2, ...
  FROM YourTableName
) AS DistinctTable;
```

This query first creates a derived table with distinct values, and then the `INTERSECT` operator finds the records that exist in both the original table and the derived table with distinct values, effectively giving you the duplicates.

4) **Use the** `ROW_NUMBER()` Function The `ROW_NUMBER()` function can also be used to identify duplicates by assigning a row number to each record within a partition defined by the columns you're checking for duplicates.

**5) Use Temporary Tables (Optional)** If you need to perform further operations on the duplicate records, you can store them in a temporary table for easier manipulation.

```sql
SELECT column1, column2, ...
INTO #TempTable
FROM (
  -- Use any of the above queries to find duplicates
);
```

Replace the **subquery** with the appropriate query from the previous steps to find the duplicates. The results will be stored in the temporary table `#TempTable`.

Remember to replace `YourTableName` with the actual name of your table, and `column1`, `column2`, etc., with the column names you want to check for duplicates.