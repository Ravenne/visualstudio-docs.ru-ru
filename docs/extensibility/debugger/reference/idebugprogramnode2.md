---
title: IDebugProgramNode2 | Документация Майкрософт
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugProgramNode2
helpviewer_keywords:
- IDebugProgramNode2 interface
ms.assetid: 80e511d8-9b40-4a85-aa5d-952fa5ee6ae7
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 51f49ca90837cf80c22856ae2e8f89a98da43d86
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62869967"
---
# <a name="idebugprogramnode2"></a>IDebugProgramNode2
Этот интерфейс представляет собой программу, которые можно отлаживать.

## <a name="syntax"></a>Синтаксис

```
IDebugProgramNode2 : IUnknown
```

## <a name="notes-for-implementers"></a>Примечания для разработчиков
 Отладчик (DE) или пользовательский порт поставщик реализует этот интерфейс для представления программы, которые можно отлаживать. Этот интерфейс обычно реализуется на тот же объект, реализующий [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md) интерфейс. Этот интерфейс зарегистрирован [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)] путем вызова [PublishProgramNode](../../../extensibility/debugger/reference/idebugprogrampublisher2-publishprogramnode.md).

## <a name="notes-for-callers"></a>Заметки о вызывающих объектов
 Вызовите [GetProviderProgramNode](../../../extensibility/debugger/reference/idebugprogramprovider2-getproviderprogramnode.md) для возвращения этого интерфейса. Пользовательский порт поставщика получает этот интерфейс, посредством вызова [AddProgramNode](../../../extensibility/debugger/reference/idebugportnotify2-addprogramnode.md). DE получает этот интерфейс, посредством вызова [Attach](../../../extensibility/debugger/reference/idebugengine2-attach.md).

## <a name="methods-in-vtable-order"></a>Методы в порядке таблицы Vtable
 В следующей таблице показаны методы `IDebugProgramNode2`.

|Метод|Описание|
|------------|-----------------|
|[GetProgramName](../../../extensibility/debugger/reference/idebugprogramnode2-getprogramname.md)|Возвращает имя программы.|
|[GetHostName](../../../extensibility/debugger/reference/idebugprogramnode2-gethostname.md)|Получает имя процесса, размещающего программы.|
|[GetHostPid](../../../extensibility/debugger/reference/idebugprogramnode2-gethostpid.md)|Получает системный идентификатор процесса для процесса, размещающего программы.|
|[GetHostMachineName_V7](../../../extensibility/debugger/reference/idebugprogramnode2-gethostmachinename-v7.md)|РЕКОМЕНДУЕТСЯ К ИСПОЛЬЗОВАНИЮ. НЕ ИСПОЛЬЗУЙТЕ.|
|[Attach_V7](../../../extensibility/debugger/reference/idebugprogramnode2-attach-v7.md)|РЕКОМЕНДУЕТСЯ К ИСПОЛЬЗОВАНИЮ. НЕ ИСПОЛЬЗУЙТЕ. См. в разделе [IDebugProgramNodeAttach2](../../../extensibility/debugger/reference/idebugprogramnodeattach2.md) интерфейс альтернативный подход.|
|[GetEngineInfo](../../../extensibility/debugger/reference/idebugprogramnode2-getengineinfo.md)|Возвращает имя и идентификатор DE, выполнение программы.|
|[DetachDebugger_V7](../../../extensibility/debugger/reference/idebugprogramnode2-detachdebugger-v7.md)|РЕКОМЕНДУЕТСЯ К ИСПОЛЬЗОВАНИЮ. НЕ ИСПОЛЬЗУЙТЕ.|

## <a name="remarks"></a>Примечания
 Диспетчер отладки сеансов (SDM) обычно вызывает [GetProviderProgramNode](../../../extensibility/debugger/reference/idebugprogramprovider2-getproviderprogramnode.md) для получения этого интерфейса.

## <a name="requirements"></a>Требования
 Заголовок: Msdbg.h

 Пространство имен: Microsoft.VisualStudio.Debugger.Interop

 Сборка: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>См. также
- [Базовые интерфейсы](../../../extensibility/debugger/reference/core-interfaces.md)
- [IDebugProgramNodeAttach2](../../../extensibility/debugger/reference/idebugprogramnodeattach2.md)
- [AddProgramNode](../../../extensibility/debugger/reference/idebugportnotify2-addprogramnode.md)
- [RemoveProgramNode](../../../extensibility/debugger/reference/idebugportnotify2-removeprogramnode.md)
- [Attach](../../../extensibility/debugger/reference/idebugengine2-attach.md)
- [GetProviderProgramNode](../../../extensibility/debugger/reference/idebugprogramprovider2-getproviderprogramnode.md)
- [PublishProgramNode](../../../extensibility/debugger/reference/idebugprogrampublisher2-publishprogramnode.md)