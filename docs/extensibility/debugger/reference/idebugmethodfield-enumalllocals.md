---
title: IDebugMethodField::EnumAllLocals | Документация Майкрософт
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugMethodField::EnumAllLocals
helpviewer_keywords:
- IDebugMethodField::EnumAllLocals method
ms.assetid: 0bc7cc13-2628-4bd8-8c06-4d2aa6755ea8
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: bbbc610dad6ab5915efe07718ad9a80592af4034
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62872994"
---
# <a name="idebugmethodfieldenumalllocals"></a>IDebugMethodField::EnumAllLocals
Создает перечислитель для всех локальных переменных метода, в том числе создаются внутри организации, с помощью компилятора.

## <a name="syntax"></a>Синтаксис

```cpp
HRESULT EnumAllLocals( 
   IDebugAddress*     pAddress,
   IEnumDebugFields** ppLocals
);
```

```csharp
int EnumAllLocals(
   IDebugAddress        pAddress,
   out IEnumDebugFields ppLocals
);
```

#### <a name="parameters"></a>Параметры
 `pAddress`

 [in] [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md) объект, представляющий адрес отладки в методе, указывающая на определенной области или контекста.

 `ppLocals`

 [out] Возвращает [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md) объект, представляющий список всех локальных переменных в указанной области; в противном случае возвращает значение null, указывающее, без локальных элементов.

## <a name="return-value"></a>Возвращаемое значение
 В случае успешного выполнения возвращает значение S_OK, или возвращает значение S_FALSE, если нет локальных переменных. В противном случае возвращается код ошибки.

## <a name="remarks"></a>Примечания
 Перечисляются только те переменные, определенные внутри блока, который содержит адрес заданной отладочной. Этот метод включает в себя все локальные переменные, создаваемые компилятором. Если все, которые требуется явно определенные в источнике, вызов "Локальные" [EnumLocals](../../../extensibility/debugger/reference/idebugmethodfield-enumlocals.md) метод.

 Метод может содержать несколько контекстов или блоки области.

## <a name="see-also"></a>См. также
- [IDebugMethodField](../../../extensibility/debugger/reference/idebugmethodfield.md)
- [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md)
- [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md)
- [EnumLocals](../../../extensibility/debugger/reference/idebugmethodfield-enumlocals.md)