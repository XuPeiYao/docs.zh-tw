---
title: "如何：使用規則運算式搜尋字串 (C# 程式設計手冊)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- searching strings [C#]
- strings [C#], searching with RegEx
ms.assetid: dcab2150-a4a2-4fe4-87e3-83b83b58d84a
caps.latest.revision: 19
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: fb05d1702c75be8fd224ee0f34d7d8d3fe71f207
ms.contentlocale: zh-tw
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-search-strings-using-regular-expressions-c-programming-guide"></a>如何：使用規則運算式搜尋字串 (C# 程式設計手冊)
<xref:System.Text.RegularExpressions.Regex?displayProperty=fullName> 類別可以用來搜尋字串。 這些搜尋的複雜度範圍可以從非常簡單到充分運用規則運算式。 以下是使用 <xref:System.Text.RegularExpressions.Regex> 類別搜尋字串的兩個範例。 如需詳細資訊，請參閱 [.NET Framework 規則運算式](https://msdn.microsoft.com/library/hs600312)。  
  
## <a name="example"></a>範例  
 下列程式碼是一個主控台應用程式，可對陣列中的字串執行簡單的不區分大小寫搜尋。 <xref:System.Text.RegularExpressions.Regex.IsMatch%2A?displayProperty=fullName> 靜態方法會執行搜尋，該搜尋已指定要搜尋的字串，且字串包含搜尋模式。 在此情況下，第三個引數用來表示應該忽略大小寫。 如需詳細資訊，請參閱<xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName>。  
  
 [!code-cs[csProgGuideStrings#17](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-search-strings-using-regular-expressions_1.cs)]  
  
## <a name="example"></a>範例  
 下列程式碼是主控台應用程式，可使用規則運算式來驗證陣列中每個字串的格式。 驗證需要每個字串採用電話號碼的形式，其中數字的三個群組以連字號分隔、前兩個群組包含三位數，而第三個群組包含四位數。 使用 `^\\d{3}-\\d{3}-\\d{4}$` 規則運算式即可完成此作業。 如需詳細資訊，請參閱[規則運算式語言 - 快速參考](http://msdn.microsoft.com/library/930653a6-95d2-4697-9d5a-52d11bb6fd4c)。  
  
 [!code-cs[csProgGuideStrings#18](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-search-strings-using-regular-expressions_2.cs)]  
  
## <a name="see-also"></a>另請參閱  
 <xref:System.Text.RegularExpressions.Regex?displayProperty=fullName>   
 [C# 程式設計手冊](../../../csharp/programming-guide/index.md)   
 [字串](../../../csharp/programming-guide/strings/index.md)   
 [.NET Framework 規則運算式](https://msdn.microsoft.com/library/hs600312)   
 [規則運算式語言 - 快速參考](http://msdn.microsoft.com/library/930653a6-95d2-4697-9d5a-52d11bb6fd4c)

