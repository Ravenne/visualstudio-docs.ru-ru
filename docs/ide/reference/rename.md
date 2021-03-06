---
title: Рефакторинг — переименование
ms.date: 01/26/2018
ms.topic: reference
author: gewarren
ms.author: gewarren
manager: jillfra
f1_keywords:
- vs.csharp.refactoring.rename
dev_langs:
- CSharp
- VB
ms.workload:
- dotnet
ms.openlocfilehash: 48e45373c41358ba3e9c2d70222ace07cdf1b59e
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62812123"
---
# <a name="rename-a-code-symbol-refactoring"></a>Рефакторинг для переименования символов кода

Область применения этого рефакторинга:

- C#

- Visual Basic

**Что?** Вы можете переименовывать идентификаторы для символов кода, например для полей, локальных переменных, методов, пространств имен, свойств и типов.

**Когда?** Вам нужно безопасно переименовать элемент без необходимости выполнять поиск всех экземпляров с последующим копированием и вставкой нового имени.

**Зачем?** Копирование и вставка нового имени во всем проекте, скорее всего, приведет к ошибкам. Это средство рефакторинга выполнит переименование без ошибок.

## <a name="how-to"></a>Практические советы

1. Выделите элемент, который требуется переименовать, или поместите в него текстовый курсор.

   - C#:

       ![Выделенный код — C#](media/rename-highlight-cs.png)

   - Visual Basic:

       ![Выделенный код — Visual Basic](media/rename-highlight-vb.png)

2. Затем выполните одно из следующих действий:

   - **Клавиатура**
      - Нажмите клавиши **CTRL+R**, а затем — **CTRL+R**. (Обратите внимание, что сочетание клавиш может отличаться в зависимости от выбранного профиля.)
   - **Мышь**
      - Последовательно выберите **Правка > Рефакторинг > Переименовать**.
      - Щелкните код правой кнопкой мыши и выберите пункт **Переименовать**.

3. Переименуйте элемент. Для этого просто введите новое имя.

   - C#:

      ![Анимация, демонстрирующая переименование, — C#](media/rename-animated-cs.gif)

   - Visual Basic:

      ![Переименование — VB](media/rename-rename-vb.png)

   > [!TIP]
   > Вы также можете обновить комментарии и другие строки, чтобы в них использовалось это новое имя. Кроме того, вы можете [просмотреть изменения](../../ide/preview-changes.md), прежде чем сохранить их. Для этого установите флажки в диалоговом окне **Переименование**, которое отображается в верхней правой части редактора.

4. Если вы довольны результатами, выберите **Применить** или нажмите клавишу **ВВОД**, чтобы зафиксировать изменения.

> [!NOTE]
> Если вы использовали уже существующее имя и это привело к конфликту, в диалоговом окне **Переименование** отобразится предупреждение.
>
> ![Конфликт переименования](media/rename-conflict-cs.png)

## <a name="see-also"></a>См. также

- [Рефакторинг](../refactoring-in-visual-studio.md)
- [Просмотр изменений](../../ide/preview-changes.md)
