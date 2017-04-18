---
title: "事件概觀 (Windows Form) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "委派 [Windows Form], 事件和"
  - "委派 [Windows Form], 多點傳送"
  - "事件 [Windows Form], 關於事件"
  - "多點傳送事件委派"
  - "Windows Form 控制項, 事件"
  - "Windows Form, 事件處理"
ms.assetid: 814a6a43-a312-4791-88d8-f75f9a4f8c4c
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# 事件概觀 (Windows Form)
事件是您可以透過程式碼加以回應或「處理」的動作。  使用者動作 \(例如按一下滑鼠按鈕或按下按鍵\)、程式碼或系統都可以產生事件。  
  
 事件導向的應用程式會以執行程式碼的方式回應事件。  每份表單與控制項都會提供一組預先定義的事件讓您進行程式設計。  當這些事件中的任何事件發生時，而相關聯的事件處理常式中含有程式碼，即會叫用該程式碼。  
  
 物件所引發的事件類型各有不同，但有許多類型為大多數控制項所共通。  例如，大部分物件都會處理 <xref:System.Windows.Forms.Control.Click> 事件。  若使用者按一下表單，便會執行表單之 <xref:System.Windows.Forms.Control.Click> 事件處理常式中的程式碼。  
  
> [!NOTE]
>  許多事件會與其他事件連帶發生。  例如在發生 <xref:System.Windows.Forms.Control.DoubleClick> 的過程中，<xref:System.Windows.Forms.Control.MouseDown>、<xref:System.Windows.Forms.Control.MouseUp> 及 <xref:System.Windows.Forms.Control.Click> 事件會連帶發生。  
  
 如需如何引發及使用事件的相關資訊，請參閱[事件](../../../docs/standard/events/index.md)。  
  
## 委派及其角色  
 委派是 [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] 中常用來建置事件處理機制的類別。  委派與函式指標大致相同，通常會在 [!INCLUDE[vcprvc](../../../includes/vcprvc-md.md)] 及其他物件導向語言中使用。  不同之處在於委派為物件導向、類型安全，安全性也較好。  除此之外，函式指標只包含特定函式的參考，而委派不僅包含了物件參考，還包含了物件中一或多個方法的參考。  
  
 此事件模型使用*「委派」*\(delegates\) 將事件繫結到要處理事件的方法。  委派允許透過指定處理常式方法的方式，為事件通知登錄其他類別。  當事件發生時，委派即會呼叫所繫結的方法。  如需有關如何定義委派的詳細資訊，請參閱[事件](../../../docs/standard/events/index.md)。  
  
 委派可以繫結到單一方法或多個方法，稱為「多點傳送」。  在為事件建立委派時，您 \(或 Windows Forms 設計工具\) 通常會建立多點傳送事件。  唯一例外是由邏輯上不會在每一事件中重複多次之特定程序 \(例如顯示對話方塊\) 所產生的事件，但此情況極為罕見。  如需有關如何建立多點傳送委派的相關資訊，請參閱[如何：組合委派 \(多點傳送委派\)](../Topic/How%20to:%20Combine%20Delegates%20\(Multicast%20Delegates\)\(C%23%20Programming%20Guide\).md)。  
  
 多點傳送委派會維護其所繫結之方法的叫用清單。  多點傳送委派可以讓 <xref:System.Delegate.Combine%2A> 方法新增方法到叫用清單，並支援 <xref:System.Delegate.Remove%2A> 方法來移除此方法。  
  
 當應用程式記錄事件時，控制項便會叫用該事件的委派來引發事件。  委派會接著呼叫所繫結的方法。  在最常見的情況 \(多點傳送委派\) 下，委派會輪流呼叫叫用清單中每一個繫結的方法，以提供一對多的通知。  此策略表示控制項無須針對事件通知而維護一份目標物件清單，因為委派會處理所有的登錄與通知事宜。  
  
 委派也可讓多個件繫結到同一方法，如此一來即可提供多對一通知。  例如按一下按鈕事件與按一下功能表命令事件都會叫用相同的委派，然後委派再呼叫一個方法，以相同方式處理這些個別的事件。  
  
 委派會隨機使用繫結機制，其可能在執行時繫結到任何簽章符合事件處理程式簽章的方法。  您可以利用此功能視條件設定或變更繫結方法，以及隨機將事件處理常式連結至控制項。  
  
## 請參閱  
 [在 Windows Form 中建立事件處理常式](../../../docs/framework/winforms/creating-event-handlers-in-windows-forms.md)   
 [事件處理常式概觀](../../../docs/framework/winforms/event-handlers-overview-windows-forms.md)