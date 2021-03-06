---
title: Преобразование локальной функции в метод
ms.date: 02/19/2019
ms.topic: reference
author: kendrahavens
ms.author: kehavens
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- dotnet
ms.openlocfilehash: ccddc3aef24ba14245dc568ca5f369e38ce8eba0
ms.sourcegitcommit: 614d5b99576ea27a41957cd94062dc95cbd29c1c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/10/2019
ms.locfileid: "65531637"
---
# <a name="convert-a-local-function-to-a-method"></a>Преобразование локальной функции в метод

Область применения этого рефакторинга:

- C#
- Visual Basic

**Что?** Преобразование локальной функции в метод.

**Когда?** У вас есть локальная функция, которую вы хотите определить за пределами текущего локального контекста.

**Зачем?** Вам нужно преобразовать локальную функцию в метод, чтобы ее можно было вызывать вне локального контекста. Преобразование в метод может понадобиться, если локальная функция становится слишком длинной. Если определить функцию в отдельный метод, код будет удобнее читать.

## <a name="convert-local-function-to-method-refactoring"></a>Рефакторинг "Преобразование локальной функции в метод"

1. Поместите курсор в локальную функцию.

    ![Пример кода для преобразования локальной функции в метод](media/convert-local-function-to-method.png)

2. Нажмите клавиши **CTRL**+**.** чтобы открыть меню **Быстрые действия и рефакторинг**.

    ![Пример исправления "Преобразование локальной функции в метод"](media/convert-local-function-to-method-codefix.png)

2. Нажмите клавишу ВВОД, чтобы принять рефакторинг.

    ![Пример результата преобразования локальной функции в метод](media/convert-local-function-to-method-result.png)

## <a name="see-also"></a>См. также

- [Рефакторинг](../refactoring-in-visual-studio.md)
- [Советы для разработчиков .NET](../csharp-developer-productivity.md)
