---
title: IDebugCanStopEvent2::GetReason | Документация Майкрософт
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugCanStopEvent2::GetReason
helpviewer_keywords:
- IDebugCanStopEvent2::GetReason
ms.assetid: f5de31ca-7b8d-4029-9cf9-ba860ac66af6
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 4f253fc622beb6eee3490b77a1531b0b2096f14a
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62877047"
---
# <a name="idebugcanstopevent2getreason"></a>IDebugCanStopEvent2::GetReason
Возвращает причину, почему хочет остановить отладчик (DE).

## <a name="syntax"></a>Синтаксис

```cpp
HRESULT GetReason( 
   CANSTOP_REASON* pcr
);
```

```csharp
int GetReason( 
   out enum_CANSTOP_REASON pcr
);
```

#### <a name="parameters"></a>Параметры
 `pcr`

 [out] Возвращает значение из [CANSTOP_REASON](../../../extensibility/debugger/reference/canstop-reason.md) перечисление, описывающее причину для данного события.

## <a name="return-value"></a>Возвращаемое значение
 В случае успешного выполнения возвращает `S_OK`; в противном случае возвращает код ошибки.

## <a name="remarks"></a>Примечания
 Этот метод обычно вызывается перед [CanStop](../../../extensibility/debugger/reference/idebugcanstopevent2-canstop.md) метод, чтобы вызывающий объект мог определить, нужно ли передать ненулевое значение (`TRUE`) для `IDebugCanStopEvent2::CanStop` метод.

 Причина остановки может быть либо `CANSTOP_ENTRYPOINT`, означающее DE достиг точки входа или `CANSTOP_STEPIN`, означающее DE шаг с заходом в функцию.

## <a name="see-also"></a>См. также
- [IDebugCanStopEvent2](../../../extensibility/debugger/reference/idebugcanstopevent2.md)
- [CANSTOP_REASON](../../../extensibility/debugger/reference/canstop-reason.md)
- [CanStop](../../../extensibility/debugger/reference/idebugcanstopevent2-canstop.md)