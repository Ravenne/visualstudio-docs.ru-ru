---
title: CA2134. Методы должны сохранять согласованную прозрачность при переопределении базовых методов | Документация Майкрософт
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2134
ms.assetid: 3b17e487-0326-442e-90e1-dc0ba9cdd3f2
caps.latest.revision: 11
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: f5c8e6298ab8ec7da947ae3c71fd2dcf4e1e9e25
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "58993048"
---
# <a name="ca2134-methods-must-keep-consistent-transparency-when-overriding-base-methods"></a>CA2134. Методы должны сохранять одинаковую прозрачность при переопределении базовых методов
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|MethodsMustOverrideWithConsistentTransparency|
|CheckId|CA2134|
|Категория|Microsoft.Security|
|Критическое изменение|Критическое|

## <a name="cause"></a>Причина
 Это правило срабатывает, когда метод, помеченный атрибутом <xref:System.Security.SecurityCriticalAttribute> переопределяет прозрачный метод или метод, помеченные с <xref:System.Security.SecuritySafeCriticalAttribute>. Это правило также применяется, когда прозрачный метод или метод, помеченные с <xref:System.Security.SecuritySafeCriticalAttribute> переопределяет метод, отмеченный атрибутом <xref:System.Security.SecurityCriticalAttribute>.

 Это правило применяется при переопределении виртуального метода или реализации интерфейса.

## <a name="rule-description"></a>Описание правила
 Это правило срабатывает при попытках изменить уровень доступности метода вверх по цепочке наследования. Например если виртуальный метод в базовом классе является прозрачным или надежным с точки зрения, затем производного класса необходимо переопределить его с прозрачный или безопасный метод. И наоборот Если виртуальный метод является критически важным для безопасности, производный класс должен переопределять его с к критическому методу безопасности. То же правило применяется для реализации методов интерфейса.

 Правила прозрачности применяются в том случае, когда код JIT-компиляцию, а не во время выполнения, поэтому расчет прозрачности не поддерживает динамическую информацию о типе. Таким образом результат расчета прозрачности должен иметь возможность определить исключительно из статических типов, JIT-компиляции, независимо от динамического типа.

## <a name="how-to-fix-violations"></a>Устранение нарушений
 Чтобы устранить нарушение этого правила, измените прозрачность метода, который переопределяет виртуальный метод или путем реализации интерфейса в соответствии с прозрачностью виртуального метода или метода интерфейса.

## <a name="when-to-suppress-warnings"></a>Отключение предупреждений
 Не следует отключать предупреждения из этого правила. Нарушение этого правила приведет к в среде выполнения, <xref:System.TypeLoadException> для сборок, которые используют прозрачность уровня 2.

## <a name="examples"></a>Примеры

### <a name="code"></a>Код
 [!code-csharp[FxCop.Security.CA2134.MethodsMustOverrideWithConsistentTransparency#1](../snippets/csharp/VS_Snippets_CodeAnalysis/fxcop.security.ca2134.methodsmustoverridewithconsistenttransparency/cs/ca2134 - methodsmustoverridewithconsistenttransparency.cs#1)]

## <a name="see-also"></a>См. также
 [Прозрачный с точки зрения безопасности код, уровень 2](http://msdn.microsoft.com/library/4d05610a-0da6-4f08-acea-d54c9d6143c0)
