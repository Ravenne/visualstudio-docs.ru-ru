---
title: Сопоставление методов в визуализации стека вызовов при отладке
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.progression.debugwithcodemaps
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- call stacks, code maps
- Call Stack window, mapping calls
- debugging [Visual Studio], diagramming the call stack
- call stacks, mapping
- Call Stack window, visualizing
- debugging code visually
- debugging [Visual Studio], mapping the call stack
- call stacks, visualizing
- debugging, code maps
- Call Stack window, tracing calls visually
- Call Stack window, show on code map
- debugging [Visual Studio], tracing the call stack visually
- debugging [Visual Studio], visualizing the call stack
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 8641a677ae36ad5a3c1f0f4344fc5c12b8798d7d
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "63445138"
---
# <a name="map-methods-on-the-call-stack-while-debugging-in-visual-studio"></a>Сопоставление методов в визуализации стека вызовов при отладке в Visual Studio

Для визуального отслеживания стека вызовов при отладке можно создать карту кода. В это сопоставление можно вносить примечания для отслеживания операций, выполняемых кодом. Таким образом, вы сможете сосредоточиться на поиске ошибок.

 ![Отладка со стеками вызовов на картах кода](../debugger/media/debuggermap_overview.png)

 Требуется:

 ::: moniker range="vs-2017"

- [Visual Studio Enterprise](https://visualstudio.microsoft.com/vs/older-downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=vs+2017+download)

::: moniker-end

::: moniker range="vs-2019"

- [Visual Studio Enterprise](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019)

::: moniker-end

- Код, который можно отлаживать, таких как Visual C#, Visual Basic, C++, JavaScript или X ++

  Пример

- [Видео. Визуальная отладка с интеграцией отладчика сопоставления кода (канал 9)](http://go.microsoft.com/fwlink/?LinkId=293418)

- [Сопоставьте стек вызовов](#MapStack)

- [Добавление примечаний в код](#MakeNotes)

- [Обновление сопоставления путем добавления следующего стека вызовов](#UpdateMap)

- [Добавление связанного кода на карту](#AddRelatedCode)

- [Поиск ошибок с помощью карты](#FindBugs)

- [ВОПРОСЫ И ОТВЕТЫ](#QA)

  Узнать о командах и действиях, которые можно использовать при работе с картами кода, см. в разделе [Просмотр и реорганизация карт кода](../modeling/browse-and-rearrange-code-maps.md).

## <a name="MapStack"></a> Сопоставление стека вызова

1. Приступите к отладке. (Клавиатура: **F5**)

2. Когда приложение переходит в режим приостановки выполнения или при входе в функцию, нажмите кнопку **карта кода**. (Клавиатура: **CTRL** + **Shift** + **`**)

     ![Выберите "Карта кода", чтобы начать формирование карты для стека вызовов](../debugger/media/debuggermap_choosecodemap.png)

     Текущий стек вызовов выделен в новой карте кода оранжевым цветом:

     ![См. стек вызовов на карте кода](../debugger/media/debuggermap_seeundocallstack.png)

     Эта карта будет автоматически обновляться в ходе отладки. См. в разделе [обновление сопоставления путем добавления следующего стека вызовов](#UpdateMap).

## <a name="MakeNotes"></a> Добавление примечаний к коду

 Добавьте комментарии, чтобы отслеживать, что происходит в коде. Чтобы добавить новую строку в комментарий, нажмите клавишу **Shift + Return**.

 ![Добавление комментария к стеку вызовов на карте кода](../debugger/media/debuggermap_addcomment.png)

## <a name="UpdateMap"></a> Обновление сопоставления путем добавления следующего стека вызовов

 Выполните приложение до следующей точки останова или зайдите в функцию. В сопоставление будет добавлен новый стек вызовов.

 ![Обновление карты кода следующим стеком вызовов](../debugger/media/debuggermap_addclearcallstack.png)

## <a name="AddRelatedCode"></a> Добавление связанного кода в сопоставление

 Теперь у вас есть карта — что далее? Если вы работаете с C# или Visual Basic, добавьте элементы, такие как поля, свойства и другие методы, чтобы отслеживать, что происходит в коде.

 Дважды щелкните метод для просмотра его определения кода или используйте контекстное меню метода. (Клавиатура: Выберите метод в сопоставлении и нажмите клавишу **F12**)

 ![Переход к определению кода метода на карте кода](../debugger/media/debuggermap_gotocodedefinition.png)

 Добавьте элементы, которые необходимо отслеживать в сопоставлении.

 ![Отображение полей в методе на карте кода со стеком вызовов](../debugger/media/debuggermap_showfields.png)

> [!NOTE]
> По умолчанию при добавлении элементов в сопоставление также добавляются узлы родительской группы, соответствующие, например, классу, пространству имен или сборке. Хотя эта возможность полезна, вы можете постоянно карты простой, отключение этой функции через **включить родительские элементы** кнопки на панели инструментов карты или нажимая клавиши **CTRL** при добавлении элементов.

 ![Поля, связанные с методом на карте кода со стеком вызовов](../debugger/media/debuggermap_showedfields.png)

 Нетрудно определить, какие методы используют одинаковые поля. Последние добавленные элементы отображаются зеленым цветом.

 Продолжайте формировать сопоставление, чтобы увидеть дополнительный код.

 ![См. методы, использующие поле: карта кода со стеком вызовов](../debugger/media/debuggermap_findallreferences.png)

 ![Методы, использующие поле на карте кода со стеком вызовов](../debugger/media/debuggermap_foundallreferences.png)

## <a name="FindBugs"></a> Поиск ошибок с помощью сопоставления

 Визуализация кода поможет вам быстрее находить ошибки. Например предположим, что вы ищите ошибку в программе для рисования. Когда вы создаете линию и пробуете отменить ее создание, ничего не происходит до тех пор, пока не будет нарисована следующая линия.

 Установив точки останова в методах `clear`, `undo` и `Repaint`, вы начинаете отладку и создаете сопоставление, аналогичное представленному ниже:

 ![Добавление другого стека вызовов на карту кода](../debugger/media/debuggermap_addpaintobjectcallstack.png)

 Учтите, что все жесты пользователя в сопоставлении вызывают метод `Repaint`, за исключением `undo`. Возможно, именно поэтому функция `undo` срабатывает не сразу.

 Когда вы исправите ошибку и продолжите выполнение программы, в сопоставление будет добавлен новый вызов из `undo` в `Repaint`.

 ![Добавление нового вызова метода в стек вызовов на карте кода](../debugger/media/debuggermap_addnewcallforrepaint.png)

## <a name="QA"></a> Вопросы и ответы

- **Не все вызовы отображаются на карте. Почему?**

   По умолчанию в сопоставлении отображается только ваш код. Чтобы просмотреть внешний код, включите его **стек вызовов** окна:

   ![Окно "Отображение внешнего кода с помощью стека вызовов"](../debugger/media/debuggermap_callstackmenu.png)

   или отключите **включить только мой код** в параметрах отладки Visual Studio:

   ![Диалоговое окно "Отображение внешнего кода с помощью параметров"](../debugger/media/debuggermap_debugoptions.png)

- **Изменение сопоставления влияет на код?**

   Изменение сопоставления не влияет на код любым способом. Можно свободно переименовать, изменить или удалить любой элемент в сопоставлении.

- **Что означает сообщение: «Диаграмме могут основываться на более старой версии кода»?**

   С момента последнего обновления сопоставления код мог измениться. Например, вызов в сопоставлении может уже не существовать в коде. Закройте сообщение, а затем попытайтесь повторить сборку решения, прежде чем повторно обновлять сопоставление.

- **Как управлять макетом сопоставления?**

   Откройте **макета** меню на панели инструментов карты:

  - Измените макет по умолчанию.

  - Чтобы остановить автоматическую перекомпоновку сопоставления, отключите режим **автоматически формировать макет при отладке**.

  - Для изменения порядка как можно реже карты, при добавлении элементов, отключите **последовательный макет**.

- **Можно ли совместно использовать карты с другими пользователями?**

   Можно экспортировать карты, отправить его другим пользователям при наличии Microsoft Outlook или сохранить его в решение, чтобы можно было вернуть в систему управления версиями.

   ![Предоставление другим пользователям доступа к карте кода со стеком вызовов](../debugger/media/debuggermap_sharewithothers.png)

- **Как остановить сопоставление добавляло новые стеки вызова автоматически?**

   Выберите ![кнопку &#45; стек вызовов Показать на карте кода автоматически](../debugger/media/debuggermap_automaticupdateicon.gif) на панели инструментов карты. Чтобы вручную добавить текущий стек вызовов на карту, нажмите клавишу **Ctrl** + **Shift** + **`**.

   По-прежнему будут выделение существующие стеки вызовов на карте, во время отладки.

- **Что значки элементов и стрелки означают?**

   Чтобы получить дополнительные сведения об элементе, наведите указатель мыши и просмотрите подсказку элемента. Вы также можете изучить **условных обозначений** чтобы узнать, что означает каждый значок.

   ![Расшифровка значков на карте кода со стеком вызовов](../debugger/media/debuggermap_showlegend.png)

  Пример

- [Сопоставьте стек вызовов](#MapStack)

- [Добавление примечаний в код](#MakeNotes)

- [Обновление сопоставления путем добавления следующего стека вызовов](#UpdateMap)

- [Добавление связанного кода на карту](#AddRelatedCode)

- [Поиск ошибок с помощью карты](#FindBugs)

## <a name="see-also"></a>См. также

- [Сопоставление зависимостей во всех решениях](../modeling/map-dependencies-across-your-solutions.md)
- [Использование карт кода для отладки приложений](../modeling/use-code-maps-to-debug-your-applications.md)
- [Поиск потенциальных проблем с помощью анализаторов карт кода](../modeling/find-potential-problems-using-code-map-analyzers.md)
- [Просмотр и реорганизация карт кода](../modeling/browse-and-rearrange-code-maps.md)
