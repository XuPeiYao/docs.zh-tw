---
title: "訊息安全性視窗 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "WS 安全性"
ms.assetid: d2221d1c-c9cb-48d1-b044-a3b4445c7f05
caps.latest.revision: 34
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 34
---
# 訊息安全性視窗
這個範例會示範如何將 <xref:System.ServiceModel.WSHttpBinding> 繫結設定成搭配 Windows 驗證使用的訊息層級安全性。  這個範例是以[使用者入門](../../../../docs/framework/wcf/samples/getting-started-sample.md)為基礎。  在這個範例中，服務會由網際網路資訊服務 \(IIS\) 裝載，而用戶端是主控台應用程式 \(.exe\)。  
  
> [!NOTE]
>  此範例的安裝程序與建置指示位於本主題的結尾。  
  
 [\<wsHttpBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)的預設安全性是使用 Windows 驗證的訊息安全性。  在這個範例中的組態檔會明確地將 [\<安全性\>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wshttpbinding.md) 的 `mode` 屬性設定為 `Message`，並且將 `clientCredentialType` 屬性設定為 `Windows`。  這些值是這個繫結的預設值，但是已經明確設定成可示範其使用方式，如下列範例組態所示。  
  
```  
<bindings>  
    <wsHttpBinding>  
        <binding>  
            <security mode="Message">  
                <message clientCredentialType="Windows"/>  
            </security>  
        </binding>  
    </wsHttpBinding>  
</bindings>  
```  
  
 用戶端端點組態是由服務端點的絕對位址、繫結及合約所組成。  用戶端繫結是透過適當的 `securityMode` 和 `authenticationMode` 所設定。  
  
```  
  
<system.serviceModel>  
  <client>  
    <endpoint address=  
            "http://localhost/servicemodelsamples/service.svc"   
            binding="wsHttpBinding"   
            bindingConfiguration="Binding1"   
            contract="Microsoft.ServiceModel.Samples.ICalculator" />  
  </client>  
  
  <bindings>  
    <wsHttpBinding>  
      <!--   
      <!--The default security for the WSHttpBinding is-->  
      <!--Message security using Windows authentication. -->  
      <!--This configuration explicitly defines the security mode -->  
      <!--as Message and the clientCredentialType as Windows  -->  
      <!--for demonstration purposes. -->  
      <binding name="Binding1">  
        <security mode="Message">  
          <message clientCredentialType="Windows"/>  
        </security>  
      </binding>  
    </wsHttpBinding>  
  </bindings>  
</system.serviceModel>  
  
```  
  
 服務原始程式碼已修改成可示範如何使用 <xref:System.ServiceModel.OperationContext.ServiceSecurityContext%2A> 存取呼叫者的身分識別。  
  
```  
public string GetCallerIdentity()  
{  
    // The Windows identity of the caller can be accessed on the ServiceSecurityContext.WindowsIdentity.  
    return OperationContext.Current.ServiceSecurityContext.WindowsIdentity.Name;  
}  
  
```  
  
 當您執行範例時，作業要求和回應會顯示在用戶端主控台視窗中。  所呼叫的第一個方法 `GetCallerIdentity`，會將呼叫者身分識別的名稱傳回給用戶端。  在主控台視窗中按 ENTER 鍵，即可關閉用戶端。  
  
### 若要安裝、建置及執行範例  
  
1.  請確定您已執行 [Windows Communication Foundation 範例的單次安裝程序](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)。  
  
2.  若要建置方案的 C\# 或 Visual Basic .NET 版本，請遵循[建置 Windows Communication Foundation 範例](../../../../docs/framework/wcf/samples/building-the-samples.md)中的指示。  
  
3.  若要在單一或跨電腦的組態中執行本範例，請遵循[執行 Windows Communication Foundation 範例](../../../../docs/framework/wcf/samples/running-the-samples.md)中的指示。  
  
## 請參閱