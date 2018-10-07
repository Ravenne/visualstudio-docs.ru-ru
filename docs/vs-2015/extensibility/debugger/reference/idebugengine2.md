---
title: IDebugEngine2 | Документация Майкрософт
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IDebugEngine2
helpviewer_keywords:
- IDebugEngine2 interface
ms.assetid: 1f0e9ac0-6dfb-461a-976c-888d82144cdb
caps.latest.revision: 16
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 38b3b6f9ba7a88d1babc60a092e4703b99d20b64
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "47568218"
---
# <a name="idebugengine2"></a>IDebugEngine2
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Последнюю версию этого раздела можно найти в [IDebugEngine2](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugengine2).  
  
Этот интерфейс представляет модуля отладки (DE). Он используется для управления различными аспектами сеанса отладки, от создания точки останова для установки и очистки исключения.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
IDebugEngine2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Примечания для разработчиков  
 Этот интерфейс реализуется пользовательский DE для управления отладки программ. Этот интерфейс должен реализовываться DE.  
  
## <a name="notes-for-callers"></a>Заметки о вызывающих объектов  
 Этот интерфейс называется диспетчером сеанса отладки (SDM) для управления сеанс отладки, включая Управление исключениями, Создание точки останова и реагирование на синхронных событий, отправленных DE.  
  
## <a name="methods-in-vtable-order"></a>Методы в порядке таблицы Vtable  
 В следующей таблице показаны методы `IDebugEngine2`.  
  
|Метод|Описание|  
|------------|-----------------|  
|[EnumPrograms](../../../extensibility/debugger/reference/idebugengine2-enumprograms.md)|Создает перечислитель для всех программ, для которого выполняется отладка, DE.|  
|[Attach](../../../extensibility/debugger/reference/idebugengine2-attach.md)|Присоединяет DE к программе.|  
|[CreatePendingBreakpoint](../../../extensibility/debugger/reference/idebugengine2-creatependingbreakpoint.md)|Создает точку останова в DE.|  
|[SetException](../../../extensibility/debugger/reference/idebugengine2-setexception.md)|Указывает порядок DE обработки данного исключения.|  
|[RemoveSetException](../../../extensibility/debugger/reference/idebugengine2-removesetexception.md)|Удаляет указанное исключение, чтобы он больше не обрабатывается ядром отладки.|  
|[RemoveAllSetExceptions](../../../extensibility/debugger/reference/idebugengine2-removeallsetexceptions.md)|Удаляет из списка исключений, заданные в интегрированной среде разработки для конкретной архитектуры среды выполнения или языка.|  
|[GetEngineID](../../../extensibility/debugger/reference/idebugengine2-getengineid.md)|Получает GUID DE.|  
|[DestroyProgram](../../../extensibility/debugger/reference/idebugengine2-destroyprogram.md)|Информирует события уничтожения, DE, что программа, указанная операция была прервана необычайно и что DE необходимо очистить все ссылки на программы и отправить программы.|  
|[ContinueFromSynchronousEvent](../../../extensibility/debugger/reference/idebugengine2-continuefromsynchronousevent.md)|Вызывается средой SDM, чтобы указать, что событие синхронной отладки, ранее отправленные DE SDM, были получены и обработаны.|  
|[SetLocale](../../../extensibility/debugger/reference/idebugengine2-setlocale.md)|Задает языковой стандарт DE.|  
|[SetRegistryRoot](../../../extensibility/debugger/reference/idebugengine2-setregistryroot.md)|Задает корневой раздел реестра, в настоящее время используется DE.|  
|[SetMetric](../../../extensibility/debugger/reference/idebugengine2-setmetric.md)|Задает метрику.|  
|[CauseBreak](../../../extensibility/debugger/reference/idebugengine2-causebreak.md)|Запросы, что все программы, отлаживаемой по этой DE остановить выполнение в следующий раз один из своих потоков пытается получить доступ.|  
  
## <a name="requirements"></a>Требования  
 Заголовок: Msdbg.h  
  
 Пространство имен: Microsoft.VisualStudio.Debugger.Interop  
  
 Сборка: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>См. также  
 [Событие](../../../extensibility/debugger/reference/idebugeventcallback2-event.md)   
 [GetEngine](../../../extensibility/debugger/reference/idebugenginecreateevent2-getengine.md)
