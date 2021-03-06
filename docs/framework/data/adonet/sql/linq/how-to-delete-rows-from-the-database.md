---
title: "HOW TO：從資料庫刪除資料列 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 2144c99b-8055-4080-a5c6-1ea14335e2a3
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# HOW TO：從資料庫刪除資料列
您可以刪除資料庫中的資料列，方法是將對應的 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 物件自其資料表相關集合中移除。[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 會將您所做的變更轉譯成適當的 SQL `DELETE` 命令。  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 不支援或辨識串聯 \(Cascade\) 刪除作業。  如果您要刪除有條件約束之資料表中的資料列，必須完成下列其中一項工作：  
  
-   在資料庫的外部索引鍵條件約束中設定 `ON DELETE CASCADE` 規則。  
  
-   使用您自己的程式碼，先刪除使父物件無法刪除的子物件。  
  
 否則，會擲回例外狀況。  請參閱本主題稍後的第二個程式碼範例。  
  
> [!NOTE]
>  您可以覆寫 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 預設方法，以執行 `Insert`、`Update` 和 `Delete` 資料庫作業。  如需詳細資訊，請參閱[自訂插入、更新和刪除作業](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md)。  
>   
>  使用 [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] 的開發人員可以使用 [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] 來開發預存程序，以達到相同的目的。  
  
 下列步驟假設一個有效的 <xref:System.Data.Linq.DataContext> 會將您連接至 Northwind 資料庫。  如需詳細資訊，請參閱[HOW TO：連接資料庫](../../../../../../docs/framework/data/adonet/sql/linq/how-to-connect-to-a-database.md)。  
  
### 若要從資料庫刪除資料列  
  
1.  查詢資料庫，以找出要刪除的資料列。  
  
2.  呼叫 <xref:System.Data.Linq.Table%601.DeleteOnSubmit%2A> 方法。  
  
3.  將變更提交至資料庫。  
  
## 範例  
 下列第一個程式碼範例會查詢資料庫中屬於訂單 \#11000 的訂單明細、將這些訂單明細標示為刪除，然後將這些變更送出至資料庫。  
  
 [!code-csharp[System.Data.Linq.Table#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.table/cs/program.cs#3)]
 [!code-vb[System.Data.Linq.Table#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.table/vb/module1.vb#3)]  
  
## 範例  
 在下列第二個範例中，目標是要移除某張訂單 \(\#10250\)。  這段程式碼會先檢查 `OrderDetails` 資料表，查看要移除的訂單是否在該處有子系。  如果訂單有子系，則會先將子系標示為移除，再將訂單標示為移除。  <xref:System.Data.Linq.DataContext> 會將實際的刪除放置在正確的訂單中，使傳送到資料庫的刪除命令得以遵守資料庫條件約束。  
  
 [!code-csharp[DLinqCascadeWorkaround#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCascadeWorkaround/cs/Program.cs#1)]
 [!code-vb[DLinqCascadeWorkaround#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCascadeWorkaround/vb/Module1.vb#1)]  
  
## 請參閱  
 [HOW TO：管理變更衝突](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)   
 [HOW TO：指派預存程序來執行更新、插入和刪除 \(O\/R 設計工具\)](../Topic/How%20to:%20Assign%20stored%20procedures%20to%20perform%20updates,%20inserts,%20and%20deletes%20\(O-R%20Designer\).md)   
 [進行和提交資料變更](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)