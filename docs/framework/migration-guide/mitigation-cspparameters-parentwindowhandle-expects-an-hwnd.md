---
title: "風險降低︰CspParameters.ParentWindowHandle 應該有 HWND |Microsoft 文件"
ms.custom: 
ms.date: 04/07/2017
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- retargeting changes
- .NET Framework 4.7 retargeting changes
- CspParameters.ParentWindowHandle
- CspParameters.ParentWindowHandle retargeting change
ms.assetid: 33264333-71d6-4d43-8827-9c98878cfea7
caps.latest.revision: 5
author: rpetrusha
ms.author: ronpet
manager: wpickett
translationtype: Human Translation
ms.sourcegitcommit: 9460c8b6ca8db927af4064e3567eca34c1bf5c91
ms.openlocfilehash: 22c258b06a5cc8fa3fec72665d7e413b0cdd11ee
ms.lasthandoff: 04/18/2017

---
# <a name="mitigation-cspparametersparentwindowhandle-expects-an-hwnd"></a>風險降低︰CspParameters.ParentWindowHandle 應該有 HWND

.NET Framework 2.0 中引進的 <xref:System.Security.Cryptography.CspParameters.ParentWindowHandle%2A> 屬性可讓應用程式註冊父視窗控制代碼值，因而存取金鑰所需的任何 UI (如 PIN 提示或同意對話方塊) 在指定的視窗會開啟為強制回應子項。 從以 .NET Framework 4.7 為目標的應用程式開始，可以將視窗控制代碼 (HWND) 指派給這個屬性。

在 .NET Framework 4.6.2 (含) 以前的 .NET Framework 版本中，指派給 <xref:System.Security.Cryptography.CspParameters.ParentWindowHandle%2A> 屬性的值必須是 <xref:System.IntPtr>，其表示 HWND 值在記憶體中的所在位置。 在 Windows 7 和舊版的 Windows 作業系統中，將該屬性設為 `form.Handle` 不會有任何作用，但在 Windows 8 和更新的版本中，則會導致 <xref:System.Security.Cryptography> 並顯示「參數不正確」訊息。

從以 .NET Framework 4.7 為目標的應用程式開始，Windows Forms 應用程式可透過以下的程式碼設定 <xref:System.Security.Cryptography.CspParameters.ParentWindowHandle%2A> 屬性：

```csharp
cspParameters.ParentWindowHandle = form.Handle;
``` 

## <a name="impact"></a>影響

以 .NET Framework 4.7 或更新版本為目標的應用程式若要註冊父視窗關聯性，建議使用以下的簡化格式︰

```csharp
cspParameters.ParentWindowHandle = form.Handle;
``` 

## <a name="mitigation"></a>緩和

開發人員如已發現正確值是 `form.Handle` 值所在之記憶體位置的位址，可以藉由將 <xref:System.Security.AppContext> 參數 `Switch.System.Security.Cryptography.DoNotAddrOfCspParentWindowHandle` 設為 `true` 以選擇退出此行為變更：

- 以程式設計方式設定 [AppContext](assetID:///T:System.Security.AppContext) 執行個體上的相容性參數。

- 將下列程式行加入至 app.config 檔案的 `<runtime>` 區段：
   
   ```xml
   <runtime>
     <AppContextSwitchOverrides value="Switch.System.Security.Cryptography.DoNotAddrOfCspParentWindowHandle=true"/>
   </runtime>
   ```

相反地，若使用者想針對執行 .NET Framework 4.7 但以舊版 .NET Framework 為目標的應用程式選擇加入新的行為，可以將 <xref:System.Security.AppContext> 參數設為 `false`。
 
## <a name="see-also"></a>請參閱

[.NET Framework 4.7 中的重定目標變更](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-7.md)

