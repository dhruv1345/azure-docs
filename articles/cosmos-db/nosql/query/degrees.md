---
title: DEGREES in Azure Cosmos DB query language
description: Learn about the DEGREES SQL system function in Azure Cosmos DB to return the corresponding angle in degrees for an angle specified in radians
author: ginamr
ms.service: cosmos-db
ms.subservice: nosql
ms.topic: conceptual
ms.date: 03/03/2020
ms.author: girobins
ms.custom: query-reference, ignite-2022
---
# DEGREES (Azure Cosmos DB)
[!INCLUDE[NoSQL](../../includes/appliesto-nosql.md)]

 Returns the corresponding angle in degrees for an angle specified in radians.  
  
## Syntax
  
```sql
DEGREES (<numeric_expr>)  
```  
  
## Arguments
  
*numeric_expr*  
   Is a numeric expression.  
  
## Return types
  
  Returns a numeric expression.  
  
## Examples
  
  The following example returns the number of degrees in an angle of PI/2 radians.  
  
```sql
SELECT DEGREES(PI()/2) AS degrees  
```  
  
 Here is the result set.  
  
```json
[{"degrees": 90}]  
```  

## Remarks

This system function will not utilize the index.

## Next steps

- [System functions Azure Cosmos DB](system-functions.yml)
- [Introduction to Azure Cosmos DB](../../introduction.md)
