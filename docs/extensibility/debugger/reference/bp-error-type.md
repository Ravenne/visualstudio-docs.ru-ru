---
title: BP_ERROR_TYPE | Документация Майкрософт
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- BP_ERROR_TYPE
helpviewer_keywords:
- BP_ERROR_TYPE enumeration
ms.assetid: c483eaab-db29-46de-bfdb-5c2a9a9cfb68
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 2964c833abfa25b57678680f8b821f992cb31de8
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/22/2019
ms.locfileid: "56689191"
---
# <a name="bperrortype"></a>BP_ERROR_TYPE
Указывает тип ошибки точки останова.

## <a name="syntax"></a>Синтаксис

```cpp
enum enum_BP_ERROR_TYPE {
    BPET_NONE            = 0x00000000,
    BPET_TYPE_WARNING    = 0x00000001,
    BPET_TYPE_ERROR      = 0x00000002,
    BPET_SEV_HIGH        = 0x0F000000,
    BPET_SEV_GENERAL     = 0x07000000,
    BPET_SEV_LOW         = 0x01000000,
    BPET_TYPE_MASK       = 0x0000ffff,
    BPET_SEV_MASK        = 0xffff0000,
    BPET_GENERAL_WARNING = BPET_SEV_GENERAL | BPET_TYPE_WARNING,
    BPET_GENERAL_ERROR   = BPET_SEV_GENERAL | BPET_TYPE_ERROR,
    BPET_ALL             = 0xffffffff
};
typedef DWORD BP_ERROR_TYPE;
```

```csharp
public enum enum_BP_ERROR_TYPE {
    BPET_NONE            = 0x00000000,
    BPET_TYPE_WARNING    = 0x00000001,
    BPET_TYPE_ERROR      = 0x00000002,
    BPET_SEV_HIGH        = 0x0F000000,
    BPET_SEV_GENERAL     = 0x07000000,
    BPET_SEV_LOW         = 0x01000000,
    BPET_TYPE_MASK       = 0x0000ffff,
    BPET_SEV_MASK        = 0xffff0000,
    BPET_GENERAL_WARNING = BPET_SEV_GENERAL | BPET_TYPE_WARNING,
    BPET_GENERAL_ERROR   = BPET_SEV_GENERAL | BPET_TYPE_ERROR,
    BPET_ALL             = 0xffffffff
};
```

## <a name="members"></a>Участники
BPET_NONE указывает не ошибка точки останова.

BPET_TYPE_WARNING идентифицирует ошибку стиле предупреждение точки останова.

BPET_TYPE_ERROR указывает ошибку стиля ошибки точки останова.

BPET_SEV_HIGH идентифицирует ошибку точки останова с высокой важностью.

BPET_SEV_GENERAL идентифицирует ошибку серьезности средняя точка останова.

BPET_SEV_LOW идентифицирует ошибку низкая серьезность точки останова.

BPET_TYPE_MASK идентифицирует ошибку стиле маска точки останова.

BPET_SEV_MASK идентифицирует ошибку серьезности маска style точки останова.

BPET_GENERAL_WARNING идентифицирует ошибку общие предупреждение style точки останова.

BPET_GENERAL_ERROR идентифицирует ошибку общие стиля ошибки точки останова.

BPET_ALL задает все типы ошибок точки останова.

## <a name="remarks"></a>Примечания
Эти значения могут объединяться с помощью побитовой `OR` и используются для `dwType` членом [BP_ERROR_RESOLUTION_INFO](../../../extensibility/debugger/reference/bp-error-resolution-info.md) структуры. Переданный в качестве параметра для [EnumErrorBreakpoints](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-enumerrorbreakpoints.md) метод.

Тип ошибки точки останова представляет собой тип и уровень серьезности. Это означает, что тип ошибки точки останова никогда не является только типа (например, `BPET_TYPE_ERROR`,) или уровнем серьезности (например, `BPET_SEV_GENERAL`) сама по себе. `BPET_GENERAL_WARNING` и `BPET_GENERAL_ERROR` предоставляют предварительно определенные значения для общих точек останова предупреждений и ошибок.

## <a name="requirements"></a>Требования
Header: msdbg.h

Пространство имен: Microsoft.VisualStudio.Debugger.Interop

Сборка: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>См. также
- [Перечисления](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)
- [BP_ERROR_RESOLUTION_INFO](../../../extensibility/debugger/reference/bp-error-resolution-info.md)
- [EnumErrorBreakpoints](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-enumerrorbreakpoints.md)
