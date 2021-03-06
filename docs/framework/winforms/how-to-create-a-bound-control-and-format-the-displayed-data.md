---
title: "如何：建立繫結控制項並格式化顯示的資料 | Microsoft Docs"
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
  - "繫結控制項 [Windows Form], 建立"
  - "繫結控制項 [Windows Form], 格式化資料"
  - "資料 [Windows Form], 格式化"
ms.assetid: d5a56228-899d-41d9-8af8-87b3f4ec2f94
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# 如何：建立繫結控制項並格式化顯示的資料
藉由 Windows Form 資料繫結，您可以使用 \[格式化和進階繫結\] 對話方塊來格式化資料繫結控制項中顯示的資料。  
  
> [!NOTE]
>  根據您目前使用的設定或版本，您所看到的對話方塊與功能表命令可能會與 \[說明\] 中描述的不同。  若要變更設定，請從 \[**工具**\] 功能表中選取 \[**匯入和匯出設定**\]。  如需詳細資訊，請參閱 [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/zh-tw/22c4debb-4e31-47a8-8f19-16f328d7dcd3)。  
  
### 繫結控制項並格式化顯示的資料  
  
1.  連接至資料來源。  
  
     如需詳細資訊，請參閱[連接資料來源](../../../docs/framework/data/adonet/connecting-to-a-data-source.md)。  
  
2.  在表單中選取控制項，然後開啟屬性視窗。  
  
3.  展開 \[\(資料繫結\)\] 屬性，然後在 \[\(進階\)\] 方塊中，按一下省略符號按鈕 \(![VisualStudioEllipsesButton 螢幕擷取畫面](../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")\) 來顯示 \[格式化和進階繫結\] 對話方塊中，具有該控制項屬性的完整清單。  
  
4.  選取您想要繫結的屬性，然後按一下 \[繫結\] 箭號。  
  
     會顯示可用資料來源清單。  
  
5.  展開您想要繫結的資料來源，直到您找到您要的單一資料項目。  
  
     例如，如果您要在資料集資料表中繫結資料行值，展開資料集的名稱，然後展開資料表名稱來顯示資料行名稱。  
  
6.  按一下要繫結項目的名稱。  
  
7.  在 \[格式類型\] 方塊中，按一下您想要套用至資料控制項中顯示的格式。  
  
     在所有情況下，如果資料來源包含 <xref:System.DBNull>，則您可以指定顯示在控制項中的值。  否則，選項會稍微不同，視您所選擇的格式類型而定。  下列表格顯示格式類型和選項。  
  
    |格式類型|格式化選項|  
    |----------|-----------|  
    |沒有格式化|沒有選項。|  
    |數值|使用 \[小數位數\] 上下按鈕控制項來指定小數位數的數字。|  
    |貨幣|使用 \[小數位數\] 上下按鈕控制項來指定小數位數的數字。|  
    |日期時間|藉由選取 \[類型\] 選取方塊中的其中一個項目，選取應如何顯示日期和時間。|  
    |科學記號|使用 \[小數位數\] 上下按鈕控制項來指定小數位數的數字。|  
    |自訂|指定使用自訂格式字串。<br /><br /> 如需詳細資訊，請參閱[格式化類型](../../../docs/standard/base-types/formatting-types.md)。 **Note:**  自訂格式字串不保證能成功地在資料來源和繫結的控制項之間反覆存取。  改為處理 <xref:System.Windows.Forms.Binding.Parse> 或 <xref:System.Windows.Forms.Binding.Format> 繫結的事件，以及在事件處理程式碼中套用自訂格式。|  
  
8.  按一下 \[確定\] 關閉 \[格式化和進階繫結\] 對話方塊並返回屬性視窗。  
  
## 請參閱  
 [如何：在 Windows Form 上建立簡單繫結控制項](../../../docs/framework/winforms/how-to-create-a-simple-bound-control-on-a-windows-form.md)   
 [Windows Form 中的使用者輸入驗證](../../../docs/framework/winforms/user-input-validation-in-windows-forms.md)   
 [Windows Form 資料繫結](../../../docs/framework/winforms/windows-forms-data-binding.md)