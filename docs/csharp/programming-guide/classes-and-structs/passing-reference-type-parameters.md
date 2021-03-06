---
title: "傳遞參考類型的參數 (C# 程式設計手冊)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- method parameters [C#], reference types
- parameters [C#], reference
ms.assetid: 9e6eb65c-942e-48ab-920a-b7ba9df4ea20
caps.latest.revision: 14
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
ms.openlocfilehash: 3f57dc9f0de6fae6da3ec8e6e6cfdc3a21baeaea
ms.contentlocale: zh-tw
ms.lasthandoff: 07/28/2017

---
# <a name="passing-reference-type-parameters-c-programming-guide"></a>傳遞參考類型的參數 (C# 程式設計手冊)
[參考型別](../../../csharp/language-reference/keywords/reference-types.md)的變數不會直接包含其資料；它會包含其資料的參考。 以傳值方式傳遞參考型別參數時，可以變更參考所指向的資料，例如類別成員的值。 不過，您無法變更參考本身的值；也就是說，您無法使用相同的參考配置記憶體給新的類別，並讓它保存在區塊外。 若要這樣做，請使用 [ref](../../../csharp/language-reference/keywords/ref.md) 或 [out](../../../csharp/language-reference/keywords/out.md) 關鍵字來傳遞參數。 為求簡化，下列範例使用 `ref`。  
  
## <a name="passing-reference-types-by-value"></a>以傳值方式傳遞參考型別  
 下列範例示範以傳值方式將 `arr` 參考型別參數傳遞至 `Change` 方法。 因為參數是對 `arr` 的參考，所以可以變更陣列元素的值。 不過，嘗試將參數重新指派至不同的記憶體位置只能在方法內運作，而且不會影響原始的 `arr` 變數。  
  
 [!code-cs[csProgGuideParameters#7](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/passing-reference-type-parameters_1.cs)]  
  
 在上述範例中，作為參考型別的 `arr` 陣列傳遞至方法時，不會使用 `ref` 參數。 在這種情況下，指向 `arr` 的參考複本會傳遞至方法。 輸出顯示方法可以變更陣列元素的內容，在此情況下為 `1` 到 `888`。 不過，在 `Change` 方法內部使用 [new](../../../csharp/language-reference/keywords/new.md) 運算子來配置新的記憶體部分，會讓 `pArray` 參數參考新的陣列。 因此，之後的任何變更將不會影響在 `Main` 內部建立的 `arr` 原始陣列。 事實上，在此範例中會建立兩個陣列，一個在 `Main` 內部，另一個在 `Change` 方法內部。  
  
## <a name="passing-reference-types-by-reference"></a>以傳址式傳遞參考型別  
 下列範例與上述範例相同，差別在於 `ref` 關鍵字會新增方法標題和呼叫。 任何在方法中進行的變更會影響呼叫端程式中的原始變數。  
  
 [!code-cs[csProgGuideParameters#8](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/passing-reference-type-parameters_2.cs)]  
  
 方法內部進行的所有變更都會影響 `Main` 中的原始陣列。 事實上，原始陣列會使用 `new` 運算子重新配置。 因此，在呼叫 `Change` 方法之後，所有對 `arr` 的參考都會指向在 `Change` 方法中建立的五個項目陣列。  
  
## <a name="swapping-two-strings"></a>交換兩個字串  
 以傳址方式傳遞參考型別參數的絶佳範例就是交換字串。 在此範例中，`str1` 和 `str2` 兩個字串會在 `Main` 中初始化，並作為 `ref` 關鍵字修改的參數傳遞給 `SwapStrings` 方法。 兩個字串也會在方法和 `Main` 內部交換。  
  
 [!code-cs[csProgGuideParameters#9](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/passing-reference-type-parameters_3.cs)]  
  
 在此範例中，參數需要以傳址方式傳遞以影響呼叫端程式中的變數。 如果您移除了方法標頭和方法呼叫中的 `ref` 關鍵字，就不會在呼叫端程式中進行任何變更。  
  
 如需字串的詳細資訊，請參閱 [string](../../../csharp/language-reference/keywords/string.md)。  
  
## <a name="see-also"></a>另請參閱  
 [C# 程式設計手冊](../../../csharp/programming-guide/index.md)   
 [傳遞參數](../../../csharp/programming-guide/classes-and-structs/passing-parameters.md)   
 [使用 ref 和 out 傳遞陣列](../../../csharp/programming-guide/arrays/passing-arrays-using-ref-and-out.md)   
 [ref](../../../csharp/language-reference/keywords/ref.md)   
 [參考型別](../../../csharp/language-reference/keywords/reference-types.md)

