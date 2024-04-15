---
title: "Find Top 10 CPU Intensive Queries"
seoTitle: "Top 10 CPU Intensive Queries in SQL Server - Find & Optimize"
seoDescription: "Identify and optimize the most CPU-intensive queries in your SQL Server database. Learn how to use SQL Server tools like Dynamic Management Views (DMVs) and"
datePublished: Thu Apr 04 2024 15:51:13 GMT+0000 (Coordinated Universal Time)
cuid: clulezfk6000009l0fvbkdkup
slug: find-top-10-cpu-intensive-queries
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1712245868002/9c600c66-fde3-4bd9-9e44-122aefa55cc7.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1712245633100/6e25d211-d7df-4817-bb39-a038344f5e08.png
tags: data, performance, data-science, databases, query

---

If you want to find the top ‘n’ queries that are currently in the cache, which are consuming more CPU, then you are at the right place.

[**<mark>sys.dm</mark>**](http://sys.dm)**<mark>_exec_query_stats</mark>** DMV contains all the information about the resource **(CPU, Memory, I/O)** consuming queries that are currently in the cache.

We can just join the above DMV with [**<mark>sys.dm</mark>**](http://sys.dm)**<mark>_exec_query_plan</mark>** and then with [**<mark>sys.dm</mark>**](http://sys.dm)**<mark>_exec_sql_text</mark>** to get query plans and SQL text that is currently executing.

**Here is the query that gives TOP 10 queries that are currently in cache that are consuming more CPU:**

```sql
;WITH eqs
AS (
    SELECT 
         [execution_count]
        ,[total_worker_time]/1000  AS [TotalCPUTime_ms]
        ,[total_elapsed_time]/1000  AS [TotalDuration_ms]
        ,query_hash
        ,plan_handle
        ,[sql_handle]
    FROM sys.dm_exec_query_stats
    )
SELECT TOP 10 est.[text], eqp.query_plan AS SQLStatement
    ,eqs.*
FROM eqs
OUTER APPLY sys.dm_exec_query_plan(eqs.plan_handle) eqp
OUTER APPLY sys.dm_exec_sql_text(eqs.sql_handle) AS est
ORDER BY [TotalCPUTime_ms] DESC
```

If we change the column in the ORDER BY to **total\_logical\_reads** column then we can find out TOP 10 I/O intensive queries. If we do a sort on the **total\_grant\_kb** column, then we can find out Memory intensive queries.

See you soon with another script.