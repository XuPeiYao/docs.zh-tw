---
title: "WHERE (Entity SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "ESQL"
ms.assetid: a8e1061e-0028-4a6f-8f19-b9f48e96c4b8
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# WHERE (Entity SQL)
WHERE 子具是直接套用在 [FROM](../../../../../../docs/framework/data/adonet/ef/language-reference/from-entity-sql.md) 子句的後面。  
  
## 語法  
  
```  
[ WHERE expression ]  
```  
  
## 引數  
 `expression`  
 布林型別。  
  
## 備註  
 WHERE 子句的語意與針對 [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] 所述者相同。  它會將來源集合的項目限制為能通過此條件者，利用這種方式來限制查詢運算式產生的物件。  
  
```  
select c from cs as c where e  
```  
  
 運算式 `e` 必須為布林型別。  
  
 WHERE 子句是直接套用在 FROM 子句之後，且在任何群組、排序或投影發生之前。  WHERE 子句的運算式可以看到 FROM 子句中定義的所有項目名稱。  
  
## 請參閱  
 [Entity SQL 參考](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)   
 [查詢運算式](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expressions-entity-sql.md)