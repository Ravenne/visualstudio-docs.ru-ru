---
title: IDebugExpressionEvaluator2::GetService | Документация Майкрософт
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- IDebugExpressionEvaluator2::GetService
- GetService
ms.assetid: f8988a9e-9d18-42af-84a7-55f41e9adf63
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: ac6f73e31e7e15a2ffd86e2d969f98a686fbd004
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62842936"
---
# <a name="idebugexpressionevaluator2getservice"></a>IDebugExpressionEvaluator2::GetService
Извлекает объект службы по заданному идентификатору.

## <a name="syntax"></a>Синтаксис

```cpp
HRESULT GetService (
   GUID        uid,
   IUnknown ** ppService
);
```

```csharp
int GetService (
   Guid       uid,
   out object ppService
);
```

#### <a name="parameters"></a>Параметры
 `uid`

 [in] Уникальный идентификатор извлекаемой службы.

 `ppService`

 [out] Возвращает объект, представляющий службу.

## <a name="return-value"></a>Возвращаемое значение
 В случае успешного выполнения возвращает `S_OK`; в противном случае возвращает код ошибки.

## <a name="remarks"></a>Примечания
 Это может быть поглощен вычислитель выражений независимых производителей для получения служб из другой средство оценки выражений. Например этот метод может использоваться для получения интерфейса для службы визуализатора из средство оценки выражений по умолчанию. Вычислители выражений сторонних вряд ли должны реализовать этот интерфейс.

## <a name="see-also"></a>См. также
- [IDebugExpressionEvaluator2](../../../extensibility/debugger/reference/idebugexpressionevaluator2.md)