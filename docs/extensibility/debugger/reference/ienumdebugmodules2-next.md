---
title: IEnumDebugModules2::Next | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IEnumDebugModules2::Next
helpviewer_keywords:
- IEnumDebugModules2::Next
ms.assetid: 46b7ccad-b07b-4ec0-b3ce-13981ffab7e8
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: c417847fc0c601f571e7bad23af07d2393f93f29
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62866911"
---
# <a name="ienumdebugmodules2next"></a>IEnumDebugModules2::Next
Возвращает следующий набор элементов из перечисления.

## <a name="syntax"></a>Синтаксис

```cpp
HRESULT Next(
   ULONG           celt,
   IDebugModule2** rgelt,
   ULONG*          pceltFetched
);
```

```csharp
int Next(
   uint            celt,
   IDebugModule2[] rgelt,
   ref uint        pceltFetched
);
```

#### <a name="parameters"></a>Параметры
 `celt`

 [in] Количество извлекаемых элементов. Также указывает максимальный размер `rgelt` массива.

 `rgelt`

 [in, out] Массив [IDebugModule2](../../../extensibility/debugger/reference/idebugmodule2.md) элементов для заполнения.

 `pceltFetched`

 [out] Возвращает количество элементов, фактически возвращенных в `rgelt`.

## <a name="return-value"></a>Возвращаемое значение
 В случае успеха возвращает `S_OK`. Возвращает `S_FALSE` меньше, чем запрошенное количество элементов может быть возвращено; в противном случае возвращает код ошибки.

## <a name="see-also"></a>См. также
- [IEnumDebugModules2](../../../extensibility/debugger/reference/ienumdebugmodules2.md)
- [IDebugModule2](../../../extensibility/debugger/reference/idebugmodule2.md)