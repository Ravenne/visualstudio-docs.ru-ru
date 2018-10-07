---
title: 'Практическое: флаг и снять отметку с потока | Документация Майкрософт'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- treads, switching [debugging]
ms.assetid: 952d579d-6911-413e-b3e5-54e7e797e70c
caps.latest.revision: 36
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: f81de0353311d11cf744487d581296500d62ecb5
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "47561808"
---
# <a name="how-to-flag-and-unflag-threads"></a>Практическое руководство. Установка и снятие отметки для потока
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Последнюю версию этого раздела можно найти в [как: по](https://docs.microsoft.com/visualstudio/debugger/how-to-flag-and-unflag-threads).  
  
Поток, которому требуется уделить особое внимание, помечая его с ним значок в можно пометить **потоков**, **Параллельные стеки**, **контроль параллельных данных**, и **GPU Потоки** windows. С помощью этого значка можно будет отличать помеченные потоки от остальных.  
  
 Отмеченные потоки также имеют специальную обработку в **потоков** списке **место отладки** панели инструментов. В списке могут отображаться все потоки или только помеченные. При пометке потока **поток** список автоматически переключается на показ только помеченных потоков, но можно переключить его обратно в режим показа всех потоков.  
  
### <a name="to-flag-or-unflag-a-thread-by-using-the-threads-window"></a>Пометка и снятие пометки потока с помощью окна "Потоки"  
  
-   В **потоков** окне Найти поток, которые вас интересуют и щелкните значок флага, чтобы выбрать или очистить флаг.  
  
### <a name="to-unflag-all-threads"></a>Сброс флагов у всех потоков  
  
-   В **потоков** , щелкните правой кнопкой мыши любой поток и выберите пункт **снять пометку со всех потоков**.  
  
### <a name="to-display-only-flagged-threads"></a>Отображение только помеченных потоков  
  
-   Нажмите кнопку флага в окне отладки.  
  
### <a name="to-flag-just-my-code"></a>Пометка только собственного кода ("Только мой код")  
  
1.  На панели инструментов в верхней части **потоков** окно, щелкните значок флага.  
  
2.  В раскрывающемся списке, нажмите кнопку **пометить только мой код**.  
  
### <a name="to-flag-threads-that-are-associated-with-selected-modules"></a>Пометка потоков, связанных с выбранными модулями  
  
1.  На панели инструментов **потоков** окно, щелкните значок флага.  
  
2.  В раскрывающемся списке, нажмите кнопку **Пометить настраиваемые выбранные модули**.  
  
3.  В **Выбор модулей** диалогового окна выберите модули, которые вы хотите.  
  
4.  (Необязательно) В **поиска** введите строку для поиска конкретных модулей.  
  
5.  Нажмите кнопку **ОК**.  
  
## <a name="see-also"></a>См. также  
 [Отладка многопоточных приложений](../debugger/debug-multithreaded-applications-in-visual-studio.md)   
 [Пошаговое руководство. Отладка многопоточных приложений](../debugger/walkthrough-debugging-a-multithreaded-application.md)


