---
title: PENDING_BP_STATE | Документация Майкрософт
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- PENDING_BP_STATE
helpviewer_keywords:
- PENDING_BP_STATE enumeration
ms.assetid: ac04ad72-fa92-4a15-ade2-0d0bbbadfc7f
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 7dd77065791d36e89c43b51dd8e1494d8e69a369
ms.sourcegitcommit: 50f0c3f2763a05de8482b3579026d9c76c0e226c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/09/2019
ms.locfileid: "65458382"
---
# <a name="pendingbpstate"></a>PENDING_BP_STATE
Указывает состояние ожидающая точка останова (точку останова, которая еще не привязаны).

## <a name="syntax"></a>Синтаксис

```cpp
enum enum_PENDING_BP_STATE { 
   PBPS_NONE     = 0x0000,
   PBPS_DELETED  = 0x0001,
   PBPS_DISABLED = 0x0002,
   PBPS_ENABLED  = 0x0003
};
typedef DWORD PENDING_BP_STATE;
```

```csharp
public enum enum_PENDING_BP_STATE { 
   PBPS_NONE     = 0x0000,
   PBPS_DELETED  = 0x0001,
   PBPS_DISABLED = 0x0002,
   PBPS_ENABLED  = 0x0003
};
```

## <a name="fields"></a>Поля
 `PBPS_NONE`\
 Заполнитель для нуля. Это значение никогда не возвращается.

 `PBPS_DELETED`\
 Указывает, что ожидающая точка останова была удалена.

 `PBPS_DISABLED`\
 Указывает, ожидающая точка останова была отключена.

 `PBPS_ENABLED`\
 Указывает, что ожидающая точка останова включена.

## <a name="remarks"></a>Примечания
 Использовать в качестве `state` членом [PENDING_BP_STATE_INFO](../../../extensibility/debugger/reference/pending-bp-state-info.md) структуры.

## <a name="requirements"></a>Требования
 Header: msdbg.h

 Пространство имен: Microsoft.VisualStudio.Debugger.Interop

 Сборка: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>См. также
- [Перечисления](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)
- [PENDING_BP_STATE_INFO](../../../extensibility/debugger/reference/pending-bp-state-info.md)