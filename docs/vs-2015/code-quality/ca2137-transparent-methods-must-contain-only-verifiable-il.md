---
title: CA2137. Прозрачные методы должны содержать только проверяемые IL | Документация Майкрософт
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2137
ms.assetid: cbaeb0e1-56b6-43b4-812a-596b2859c329
caps.latest.revision: 15
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 2876a70eedb1191aaed91204505286f97e00a27b
ms.sourcegitcommit: c496a77add807ba4a29ee6a424b44a5de89025ea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2019
ms.locfileid: "58991600"
---
# <a name="ca2137-transparent-methods-must-contain-only-verifiable-il"></a>CA2137. Прозрачные методы должны содержать только поддающийся проверке промежуточный язык
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|TransparentMethodsMustBeVerifiable|
|CheckId|CA2137|
|Категория|Microsoft.Security|
|Критическое изменение|Критическое|

## <a name="cause"></a>Причина
 Метод содержит непроверяемый код или возвращает тип по ссылке.

## <a name="rule-description"></a>Описание правила
 Это правило срабатывает при попытках прозрачного кода безопасности выполнить непроверяемый MSIL. Однако это правило не содержит полную проверку IL, и вместо нее использует эвристику для выявления большинства нарушений проверки MSIL.

 Чтобы быть уверенным, что ваш код содержит только проверяемый код MSIL, запустите [Peverify.exe (средство PEVerify)](http://msdn.microsoft.com/library/f4f46f9e-8d08-4e66-a94b-0c69c9b0bbfa) для сборки. Запустите PEVerify с **/ прозрачного** параметр, который ограничивает выходные данные только непроверяемый прозрачные методы которых приведет к ошибке. Если / прозрачного параметр не используется, PEVerify также проверяет критические методы, которые могут содержать непроверяемый код.

## <a name="how-to-fix-violations"></a>Устранение нарушений
 Чтобы устранить нарушение этого правила, пометьте метод <xref:System.Security.SecurityCriticalAttribute> или <xref:System.Security.SecuritySafeCriticalAttribute> атрибут, или удалите непроверяемый код.

## <a name="when-to-suppress-warnings"></a>Отключение предупреждений
 Для этого правила отключать вывод предупреждений не следует.

## <a name="example"></a>Пример
 В данном примере метод использует непроверяемый код и должны быть помечены <xref:System.Security.SecurityCriticalAttribute> или <xref:System.Security.SecuritySafeCriticalAttribute> атрибута.

 [!code-csharp[FxCop.Security.CA2137.TransparentMethodsMustBeVerifiable#1](../snippets/csharp/VS_Snippets_CodeAnalysis/fxcop.security.ca2137.transparentmethodsmustbeverifiable/cs/ca2137 - transparentmethodsmustbeverifiable.cs#1)]
