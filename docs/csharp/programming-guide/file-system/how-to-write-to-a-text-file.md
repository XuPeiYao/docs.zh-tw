---
title: "如何：寫入文字檔 (C# 程式設計手冊)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- TextWriter.WriteLine
- StreamWriter.Close
dev_langs:
- CSharp
helpviewer_keywords:
- files [C#], text files
- text, writing to files [C#]
ms.assetid: 2e99f184-d88b-4719-a7f1-d9ec482aa809
caps.latest.revision: 23
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 12a74a5664a8f514c89d9de3ce470c98319f84d2
ms.contentlocale: zh-tw
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-write-to-a-text-file-c-programming-guide"></a>如何：寫入文字檔 (C# 程式設計手冊)
在下列這些範例中，會示範幾個將文字寫入檔案的方法。  前兩個範例會在 <xref:System.IO.File?displayProperty=fullName> 類別上使用靜態便利方法，將任何 IEnumerable\<字串> 的每個項目和字串寫入文字檔。  範例 3 中會示範寫入檔案時，如何在需要分別處理每一行時，將文字加入至檔案。  範例 1-3 會覆寫檔案中所有現有的內容，但是範例 4 將示範如何將文字附加至現有的檔案。  
  
 這些範例全都會將字串常值寫入至檔案，不過您可能比較想要使用 <xref:System.String.Format%2A> 方法，該方法提供許多控制項讓您撰寫不同類型的值，在欄位中靠右或靠左對齊、使用或不使用邊框間距等等。  您也可以使用 C# [字串插值](../../../csharp/language-reference/keywords/interpolated-strings.md)功能。  
  
## <a name="example"></a>範例  
 [!code-cs[csFilesandFolders#3](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-write-to-a-text-file_1.cs)]  
  
 這些範例全都會將字串常值寫入至檔案，不過您可能比較想要使用 <xref:System.String.Format%2A> 方法，該方法提供許多控制項讓您撰寫不同類型的值，在欄位中靠右或靠左對齊、使用或不使用邊框間距等等。  您也可以使用 C# [字串插值](../../../csharp/language-reference/keywords/interpolated-strings.md)功能。  
  
## <a name="robust-programming"></a>穩固程式設計  
 以下條件可能會造成例外狀況：  
  
-   該檔案存在而且是唯讀的。  
  
-   路徑名稱可能太長。  
  
-   磁碟可能已滿。  
  
## <a name="see-also"></a>另請參閱  
 [C# 程式設計手冊](../../../csharp/programming-guide/index.md)   
 [檔案系統和登錄 (C# 程式設計手冊)](../../../csharp/programming-guide/file-system/index.md)   
 [範例：如何將集合儲存至應用程式儲存空間](http://code.msdn.microsoft.com/CSWinStoreAppSaveCollection-bed5d6e6)

