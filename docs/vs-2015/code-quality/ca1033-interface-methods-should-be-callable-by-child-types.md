---
title: CA1033. Методы интерфейса должны быть дочерним типам | Документация Майкрософт
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- InterfaceMethodsShouldBeCallableByChildTypes
- CA1033
helpviewer_keywords:
- CA1033
- InterfaceMethodsShouldBeCallableByChildTypes
ms.assetid: 9f171497-a5e3-4769-a77b-7aed755b2662
caps.latest.revision: 19
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: e43944a3a21f48559ab5bf36d30585f8550b9da1
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "58978954"
---
# <a name="ca1033-interface-methods-should-be-callable-by-child-types"></a>CA1033. Методы интерфейса должны быть доступны для вызова дочерними типами
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|InterfaceMethodsShouldBeCallableByChildTypes|
|CheckId|CA1033|
|Категория|Microsoft.Design|
|Критическое изменение|Не критическое|

## <a name="cause"></a>Причина
 Незапечатанный тип, доступный для внешнего кода, предоставляет явную реализацию метода открытого интерфейса и не предоставляет доступный для внешнего кода альтернативный метод с тем же именем.

## <a name="rule-description"></a>Описание правила
 Рассмотрим базовый тип, который явно реализует открытый метод интерфейса. Тип, производный от базового типа можно обращаться из метода наследуемого интерфейса только ссылку на текущий экземпляр (`this` в C#), приведение к интерфейсу. Если производный тип повторно реализует (явно) наследованный метод интерфейса, базовая реализация больше не доступен. Вызов через ссылки на текущий экземпляр будет вызывать производной реализации; Это приводит к рекурсии и возможному переполнению стека.

 Это правило не сообщает о нарушениях для явной реализации <xref:System.IDisposable.Dispose%2A?displayProperty=fullName> при доступном `Close()` или `System.IDisposable.Dispose(Boolean)` предоставляется метод.

## <a name="how-to-fix-violations"></a>Устранение нарушений
 Чтобы устранить нарушение этого правила, реализуйте новый метод, который предоставляет те же функциональные возможности и видим для производных типов, или измените на реализацию неявными. Если допустима является критическим изменением, альтернативой является сделайте тип запечатанным.

## <a name="when-to-suppress-warnings"></a>Отключение предупреждений
 Его можно безопасно подавить предупреждение из этого правила, если видимый извне метод предоставляется, имеет ту же функциональность, но отличается от имени явной реализации метода.

## <a name="example"></a>Пример
 В следующем примере показано типом, `ViolatingBase`, который нарушает правило и тип `FixedBase`, демонстрирующий Устранение нарушения.

 [!code-csharp[FxCop.Design.ExplicitMethodImplementations#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.ExplicitMethodImplementations/cs/FxCop.Design.ExplicitMethodImplementations.cs#1)]

## <a name="see-also"></a>См. также
 [Интерфейсы](http://msdn.microsoft.com/library/2feda177-ce11-432d-81b4-d50f5f35fd37)
