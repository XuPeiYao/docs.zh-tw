---
title: "泛型介面 (C# 程式設計手冊)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- C# language, generic interfaces
- generics [C#], interfaces
ms.assetid: a8fa49a1-6e78-4a09-87e5-84a0b9f5ffbe
caps.latest.revision: 28
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
ms.openlocfilehash: 2a9a994c339553b923b930660c0e129dd930de96
ms.contentlocale: zh-tw
ms.lasthandoff: 07/28/2017

---
# <a name="generic-interfaces-c-programming-guide"></a>泛型介面 (C# 程式設計手冊)
定義表示集合中項目的泛型集合類別或泛型類別的介面，通常會很有用。 泛型類別的喜好設定會使用泛型介面，例如 <xref:System.IComparable%601> 而不是 <xref:System.IComparable>，以避免實值型別的 boxing 和 unboxing 作業。 .NET Framework 類別庫會定義數個泛型介面，搭配 <xref:System.Collections.Generic> 命名空間中的集合類別使用。  
  
 將介面指定為型別參數的條件約束時，只能使用使用實作介面的類型。 下列程式碼範例示範衍生自 `GenericList<T>` 類別的 `SortedList<T>` 類別。 如需詳細資訊，請參閱[泛型簡介](../../../csharp/programming-guide/generics/introduction-to-generics.md)。 `SortedList<T>` 會新增條件約束 `where T : IComparable<T>`。 這可讓 `SortedList<T>` 的 `BubbleSort` 方法使用 List 元素上的泛型 <xref:System.IComparable%601.CompareTo%2A> 方法。 在此範例中，List 元素是簡單的類別 `Person`，它會實作 `IComparable<Person>`。  
  
 [!code-cs[csProgGuideGenerics#29](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-interfaces_1.cs)]  
  
 多個介面可以指定為單一類型上的條件約束，如下所示：  
  
 [!code-cs[csProgGuideGenerics#30](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-interfaces_2.cs)]  
  
 介面可以定義多個型別參數，如下所示：  
  
 [!code-cs[csProgGuideGenerics#31](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-interfaces_3.cs)]  
  
 適用於類別的繼承規則也適用於介面：  
  
 [!code-cs[csProgGuideGenerics#32](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-interfaces_4.cs)]  
  
 如果泛型介面是 contra-variant，泛型介面可以繼承自非泛型介面，這表示它只會使用其型別參數做為傳回值。 在 .NET Framework 類別庫中，<xref:System.Collections.Generic.IEnumerable%601> 繼承自 <xref:System.Collections.IEnumerable>，因為在 <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> 的傳回值和 <xref:System.Collections.Generic.IEnumerator%601.Current%2A> 屬性 getter 中，<xref:System.Collections.Generic.IEnumerable%601> 只會使用 `T`。  
  
 實體類別可以實作封閉式建構介面，如下所示：  
  
 [!code-cs[csProgGuideGenerics#33](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-interfaces_5.cs)]  
  
 泛型類別可以實作泛型介面或封閉式建構介面，只要類別參數清單提供介面需要的所有引數，如下所示：  
  
 [!code-cs[csProgGuideGenerics#34](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-interfaces_6.cs)]  
  
 控制方法多載的規則，和用於泛型類別、泛型結構或泛型介面中的方法的規則一樣。 如需詳細資訊，請參閱[泛型方法](../../../csharp/programming-guide/generics/generic-methods.md)。  
  
## <a name="see-also"></a>另請參閱  
 [C# 程式設計手冊](../../../csharp/programming-guide/index.md)   
 [泛型簡介](../../../csharp/programming-guide/generics/introduction-to-generics.md)   
 [interface](../../../csharp/language-reference/keywords/interface.md)   
 [泛型](~/docs/standard/generics/index.md)

