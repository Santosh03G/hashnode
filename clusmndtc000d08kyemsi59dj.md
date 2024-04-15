---
title: "Search Database Objects"
datePublished: Tue Apr 09 2024 17:00:11 GMT+0000 (Coordinated Universal Time)
cuid: clusmndtc000d08kyemsi59dj
slug: search-database-objects
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1712681974201/288300a2-daf3-4ba7-844a-a4e8c58572ec.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1712681992761/7fa49f14-fc7f-4a6e-b5b3-707fbbf0ada9.png
tags: data, data-science, databases, data-structures

---

A stored procedure to search database objects (triggers, scalar functions, table valued functions, views and stored procedures) for a user defined string.

```sql
IF OBJECT_ID (N'dbo.sp_SearchDBObjects', N'P') IS NOT NULL  
   DROP PROCEDURE sp_SearchDBObjects;  
GO  

CREATE PROCEDURE dbo.sp_SearchDBObjects (@String varchar(max))  

AS   

BEGIN  

SELECT 
  
 CASE WHEN O.TYPE = 'TR' THEN 'Trigger'
  WHEN O.TYPE = 'FN' THEN 'Scalar Function'
  WHEN O.TYPE = 'IF' THEN 'Table Valued Function'
  WHEN O.TYPE = 'V' THEN 'View'
  WHEN O.TYPE = 'P' THEN 'Stored Procedure'
  ELSE NULL END AS [Object Type],  
 S.NAME + '.' + O.NAME AS [Object Name],
 M.DEFINITION AS [Object Code]
FROM
   SYS.SQL_MODULES AS m
   INNER JOIN SYS.OBJECTS AS O ON M.OBJECT_ID = O.OBJECT_ID
   INNER JOIN SYS.SCHEMAS AS S ON O.SCHEMA_ID = S.SCHEMA_ID
WHERE
O.TYPE IN
('TR', 'FN', 'IF', 'V', 'P')
AND
M.DEFINITION LIKE '%' + @String + '%'

END
```