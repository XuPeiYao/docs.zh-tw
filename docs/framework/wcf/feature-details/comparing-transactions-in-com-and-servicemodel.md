---
title: "比較 COM+ 與 ServiceModel 的交易 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e493bcdd-b91a-4486-853f-83dbcd1931b7
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# 比較 COM+ 與 ServiceModel 的交易
這個主題會討論如何使用 <xref:System.ServiceModel> 命名空間提供的 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 屬性，來模擬交易 COM\+ 服務的行為。  
  
## 使用 ServiceModel 屬性模擬 COM\+  
 下列表格會比較用來建立 `EnterpriseServices` 交易的 <xref:System.EnterpriseServices.TransactionOption> 列舉，以及如何與 <xref:System.ServiceModel> 命名空間提供的 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 屬性產生關聯。  
  
|COM\+ 屬性|[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 屬性|  
|--------------|----------------------------------------------------------------|  
|RequiresNew|<xref:System.ServiceModel.TransactionFlowAttribute> 設定為 <xref:System.ServiceModel.TransactionFlowOption>。<br /><br /> <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> 為 `true`。<br /><br /> 繫結項目中的 `TransactionFlow` 屬性為 `false`。|  
|必要項|<xref:System.ServiceModel.TransactionFlowAttribute> 設定為 <xref:System.ServiceModel.TransactionFlowOption>。<br /><br /> <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> 為 `true`。<br /><br /> 繫結項目中的 `TransactionFlow` 屬性為 `true`。|  
|支援|沒有直接的對等項目。  一般來說，您應該採用對 `Required` 所指定的行為。|  
|NotSupported|<xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> 為 `false`。<br /><br /> 繫結項目中的 `TransactionFlow` 屬性為 `false`。|  
|已停用|沒有直接的對等項目。  一般來說，您應該採用對 `NotSupported` 所指定的行為。|