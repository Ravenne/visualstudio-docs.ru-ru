---
title: CA2121. Статические конструкторы должны быть частными
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA2121
- StaticConstructorsShouldBePrivate
helpviewer_keywords:
- CA2121
- StaticConstructorsShouldBePrivate
ms.assetid: ee93c620-8fc1-4e47-866c-d389c3ca9f2e
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 9aecfe8e0be0f5d32df41b7eb164423fd4d405db
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62545007"
---
# <a name="ca2121-static-constructors-should-be-private"></a>CA2121. Статические конструкторы должны быть частными

|||
|-|-|
|TypeName|StaticConstructorsShouldBePrivate|
|CheckId|CA2121|
|Категория|Microsoft.Security|
|Критическое изменение|Критическое|

## <a name="cause"></a>Причина

Тип имеет статический конструктор, который не является закрытым.

## <a name="rule-description"></a>Описание правила

Статический конструктор, также известный как конструктор класса, используется для инициализации типа. Система вызывает статический конструктор перед созданием первого экземпляра типа или ссылкой на любые статические члены. Пользователь имеет не контролирует, когда вызывается статический конструктор. Если статический конструктор не является закрытым, он может быть вызван кодом, находящимся за пределами системы. В зависимости от операций, выполняемых в конструкторе, это может стать причиной непредвиденного поведения

Это правило применяется компиляторами C# и Visual Basic.

## <a name="how-to-fix-violations"></a>Устранение нарушений

Нарушения обычно вызваны одной из следующих действий:

- Определен статический конструктор для типа и не поступивший закрытый.

- Компилятор языка программирования добавлен статический конструктор по умолчанию к типу и не поступивший закрытый.

Чтобы устранить нарушение первого типа, сделайте ваш статический конструктор закрытым. Чтобы устранить второго типа, добавьте закрытый статический конструктор для данного типа.

## <a name="when-to-suppress-warnings"></a>Отключение предупреждений

Не следует отключать эти нарушения. Если программе требуется явный вызов в статическом конструкторе, весьма вероятно, что проект содержит серьезные недостатки и должны быть проверены.