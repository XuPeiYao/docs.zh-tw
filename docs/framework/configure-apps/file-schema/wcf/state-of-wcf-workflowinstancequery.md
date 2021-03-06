---
title: "WCF 的 &lt;state&gt;、&lt;workflowInstanceQuery&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 40f21055-766c-4be9-86c4-d1d899007098
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# WCF 的 &lt;state&gt;、&lt;workflowInstanceQuery&gt;
表示建立追蹤記錄時，追蹤的工作流程執行個體中的訂閱狀態集合。  
  
 如需追蹤設定檔查詢的詳細資訊，請參閱[追蹤設定檔](../../../../../docs/framework/windows-workflow-foundation//tracking-profiles.md)。  
  
## 語法  
  
```vb  
  
<tracking>  
   <trackingProfile name="Name">  
       <workflow>  
          <workflowInstanceQueries>  
             <workflowInstanceQuery>  
                <states>  
                   <state name="Name"/>  
                </states>  
            </workflowInstanceQuery>  
         </workflowInstanceQueries>  
       </workflow>  
   </trackingProfile>  
</tracking>  
  
```  
  
## 屬性和項目  
 下列章節說明屬性、子項目和父項目。  
  
### 屬性  
  
|屬性|描述|  
|--------|--------|  
|name|字串，可指定建立追蹤記錄時，追蹤的工作流程執行個體中的訂閱狀態。|  
  
### 子項目  
 無。  
  
### 父項目  
  
|項目|描述|  
|--------|--------|  
|[\<states\>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)|建立追蹤記錄時，追蹤的工作流程執行個體中的訂閱狀態集合。|  
  
## 備註  
 按照此集合中的狀態篩選傳回的記錄。  
  
 下表說明可能的狀態值。  
  
|狀態|描述|  
|--------|--------|  
|已中止|工作流程執行個體已中止。|  
|已完成|工作流程執行個體已完成。|  
|Deleted|工作流程執行個體已刪除。|  
|閒置|工作流程執行個體閒置中。|  
|已保存|工作流程執行個體已保存。|  
|已繼續|工作流程執行個體已繼續。|  
|已啟動|工作流程執行個體已啟動。|  
|未處理的例外狀況|工作流程執行個體發生未處理的例外狀況。|  
|Unloaded|工作流程執行個體已卸載。|  
|已取消|工作流程執行個體已取消。|  
|暫停|工作流程執行個體已暫停。|  
|已終止|工作流程執行個體已終止。|  
|Unsuspended|工作流程執行個體已取消暫停。|  
  
## 範例  
 下列組態可使用這個查詢，訂閱 `Started` 執行個體狀態之工作流程執行個體層級的追蹤記錄。  
  
```  
  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
  
```  
  
## 請參閱  
 [System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement](assetId:///System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?qualifyHint=False&amp;autoUpgrade=True)   
 [System.ServiceModel.Activities.Tracking.Configuration.StateElement](assetId:///System.ServiceModel.Activities.Tracking.Configuration.StateElement?qualifyHint=False&amp;autoUpgrade=True)   
 [System.Activities.Tracking.WorkflowInstanceQuery](assetId:///System.Activities.Tracking.WorkflowInstanceQuery?qualifyHint=False&amp;autoUpgrade=True)   
 [工作流程追蹤與追查](../../../../../docs/framework/windows-workflow-foundation//workflow-tracking-and-tracing.md)   
 [追蹤設定檔](../../../../../docs/framework/windows-workflow-foundation//tracking-profiles.md)