---
title: IDebugQueryEngine2::GetEngineInterface | Документация Майкрософт
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugQueryEngine2::GetEngineInterface
helpviewer_keywords:
- IDebugQueryEngine2::GetEngineInterface
ms.assetid: ed84aa98-7ec7-48f3-97ae-821090bc3664
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: af67f4589682cc3c0ecf42653374521c011115c2
ms.sourcegitcommit: 50f0c3f2763a05de8482b3579026d9c76c0e226c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/09/2019
ms.locfileid: "65457527"
---
# <a name="idebugqueryengine2getengineinterface"></a>IDebugQueryEngine2::GetEngineInterface
Получает интерфейс отладки ядра (DE).

## <a name="syntax"></a>Синтаксис

```cpp
HRESULT GetEngineInterface( 
   IUnknown** ppUnk
);
```

```csharp
int GetEngineInterface( 
   out object ppUnk
);
```

## <a name="parameters"></a>Параметры
 `ppUnk`\

 [out] Возвращает `IUnknown` объект представляет модуль отладки (DE), и который можно запросить для любого другого допустимым интерфейса, связанные с Развернутой (например [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md) или [IDebugEngineLaunch2](../../../extensibility/debugger/reference/idebugenginelaunch2.md)).

## <a name="return-value"></a>Возвращаемое значение
 В случае успешного выполнения возвращает `S_OK`; в противном случае возвращает код ошибки.

## <a name="remarks"></a>Примечания
 Итоговый интерфейс следует использовать с осторожностью, так как вызов через интерфейсы, полученные из этого метода позволяет обойти диспетчер отладки сеансов обработки и может привести к SDM в некорректном состоянии или вызвали ошибку во время отладки.

## <a name="see-also"></a>См. также
- [IDebugQueryEngine2](../../../extensibility/debugger/reference/idebugqueryengine2.md)
- [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md)
- [IDebugEngineLaunch2](../../../extensibility/debugger/reference/idebugenginelaunch2.md)