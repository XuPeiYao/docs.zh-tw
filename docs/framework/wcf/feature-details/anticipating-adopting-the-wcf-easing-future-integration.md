---
title: "預計採用 Windows Communication Foundation：簡化未來整合 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 3028bba8-6355-4ee0-9ecd-c56e614cb474
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# 預計採用 Windows Communication Foundation：簡化未來整合
如果您正使用 ASP.NET，並且預期會在未來使用 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]，此主題提供指引以確定新的 ASP.NET Web 服務與 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 應用程式能夠順利搭配運作。  
  
## 一般建議  
 任何新服務都採用 ASP.NET 2.0。如此一來就能使用新版本的改進與增強功能。但是，也可能會發生在相同的應用程式中同時使用 ASP.NET 2.0 與 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 元件。  
  
## 通訊協定  
 使用 ASP.NET 2.0 的新功能以驗證是否符合 WS\-I Basic Profile 1.1：  
  
```  
[WebService(Namespace = "http://tempuri.org/")]  
[WebServiceBinding(  
     ConformsTo = WsiProfiles.BasicProfile1_1,  
     EmitConformanceClaims=true)]  
public interface IEcho  
  
```  
  
 符合 WS\-I Basic Profile 1.1 的 ASP.NET Web 服務可以藉由使用 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 預先定義繫結 <xref:System.ServiceModel.BasicHttpBinding>，能夠與 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 用戶端互通。  
  
## 服務開發  
 請避免使用 <xref:System.Web.Services.Protocols.SoapDocumentServiceAttribute> 屬性讓訊息不根據 SOAPAction HTTP 標頭而根據 SOAP 訊息的本文項目完整名稱傳送到方法。[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 會使用 SOAPAction HTTP 標頭傳送訊息。  
  
## 資料表示  
 根據預設，<xref:System.Xml.Serialization.XmlSerializer> 序列化型別的目標 XML 在語意上與 <xref:System.Runtime.Serialization.DataContractSerializer> 序列化型別的目標 XML 是一樣的 \(前提是 XML 的命名空間已明確定義\)。當定義要與在未來可能會採用 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 之 ASP.NET Web 服務一起使用的資料型別時，請執行下列步驟：  
  
1.  使用 .NET Framework 類別，而不是 XML 結構描述來定義型別。  
  
2.  僅將 <xref:System.SerializableAttribute> 和 <xref:System.Xml.Serialization.XmlRootAttribute> 新增至類別，並使用後者明確定義該型別的命名空間。請勿從 <xref:System.Xml.Serialization> 命名空間新增其他屬性，以控制 .NET Framework 類別轉譯成 XML 的方式。  
  
 採用這個方法之後，您稍後應該可以藉由新增 <xref:System.Runtime.Serialization.DataContractAttribute> 和 <xref:System.Runtime.Serialization.DataMemberAttribute>，將 .NET 類別納入資料合約中，而不用特別提醒針對傳輸需要而序列化類別的目標 XML。ASP.NET Web 服務在訊息中使用的型別，[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 應用程式能夠將其當做資料合約處理，提供除了其他益處以外更好的 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 應用程式效能。  
  
## 安全性  
 請避免使用網際網路資訊服務 \(IIS\) 提供的驗證選項。[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 用戶端並不支援這些選項。如果需要保護服務安全，請使用 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 提供的選項，因為這些選項的用途更廣並且是根據標準通訊協定。  
  
## 請參閱  
 [預計採用 Windows Communication Foundation：簡化未來移轉](../../../../docs/framework/wcf/feature-details/anticipating-adopting-wcf-migration.md)