---
title: Задачи отладки | Документация Майкрософт
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], tasks
ms.assetid: 5d60e9e8-305e-4a48-829f-b9440fc8af7b
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 299db84fb06679bfbf9dff92234c944cbdec6295
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62925821"
---
# <a name="debug-tasks"></a>Отладка задач
Чтобы отладить программу, необходимо запустить и модуля отладки (DE) должен быть подключен к нему, иначе DE должен быть подключен к ранее запущенные программы. После присоединения DE необходимо создать определенные события запуска. В ответ отладочный пакет пытается выполнить привязку точки останова, заданные в интегрированной среде разработки. Когда программа достигает связанная точка останова, он прерывается и ждет ввод пользователя.

## <a name="in-this-section"></a>Содержание раздела
 [Проблемы безопасности](../../extensibility/debugger/security-issues.md) приведены инструкции безопасности, которые необходимы для отладки программы.

 [Запуск программы](../../extensibility/debugger/launching-a-program.md) содержит пошаговые инструкции по указанию DE, который вызывает операционной системы, чтобы запустить программу.

 [Присоединиться к программе](../../extensibility/debugger/attaching-directly-to-a-program.md) описывает процесс, используемый для отладки программы, в процессе, который уже выполняется.

 [Отправка событий запуска после запуска](../../extensibility/debugger/sending-startup-events-after-a-launch.md) перечислены события, происходящие после DE присоединяется к программе, пока программа не в основной точки входа и готов для отладки.

 [Элемент управления выполнения](../../extensibility/debugger/control-of-execution.md) объясняет, как DE обычно отправляет событие точки входа, событие завершения нагрузки или событии остановки, в зависимости от обстоятельств.

 [Привязка точки останова](../../extensibility/debugger/binding-breakpoints.md) описывает, как это сделать, если пользователь устанавливает точку останова, среда IDE формирует запрос и запрашивает у сеанса отладки, чтобы создать точку останова.

 [Вычисление выражений](../../extensibility/debugger/evaluating-expressions.md) объясняется, как создавать выражения и что происходит при вычислении выражения.

 [Визуализация и просмотр данных](../../extensibility/debugger/visualizing-and-viewing-data.md) объясняет, как с помощью вычислителя выражений (EE) поддерживаются визуализаторов типов и пользовательских средств просмотра.

## <a name="related-sections"></a>Связанные разделы
 [Отладчик: основные понятия](../../extensibility/debugger/debugger-concepts.md) описывает основные архитектурные понятия отладки.

 [Компоненты отладчика](../../extensibility/debugger/debugger-components.md) Общие сведения о Visual Studio, отладка компонентов, которые включают DE, EE и обработчик символов (SH).

 [Контексты отладчика](../../extensibility/debugger/debugger-contexts.md) объясняет, как DE одновременно работает в контекстах оценки кода, документацию и выражение. Описание для каждого из трех контекстов, расположение, положения или оценки, относящиеся к его.

## <a name="see-also"></a>См. также
 [Начало работы](../../extensibility/debugger/getting-started-with-debugger-extensibility.md)