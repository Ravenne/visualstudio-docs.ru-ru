---
title: IDebugCustomAttributeQuery2::IsCustomAttributeDefined | Документация Майкрософт
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugCustomAttributeQuery2::IsCustomAttributeDefined
helpviewer_keywords:
- IDebugCustomAttributeQuery2::IsCustomAttributeDefined
ms.assetid: 5c07cc52-6d2d-42df-9d76-9f1f769641db
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 6695753fa1b071f8623b079dbe4e56e68e9dfad4
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62876028"
---
# <a name="idebugcustomattributequery2iscustomattributedefined"></a>IDebugCustomAttributeQuery2::IsCustomAttributeDefined
Определяет, существует ли настраиваемый атрибут по имени.

## <a name="syntax"></a>Синтаксис

```cpp
HRESULT IsCustomAttributeDefined( 
   LPCOLESTR pszCustomAttributeName
);
```

```csharp
int IsCustomAttributeDefined(
   [In] string pszCustomAttributeName
);
```

#### <a name="parameters"></a>Параметры
 `pszCustomAttributeName`

 [in] Строка, содержащая имя настраиваемого атрибута для поиска.

## <a name="return-value"></a>Возвращаемое значение
 Возвращает значение S_OK, если настраиваемого атрибута определен на это поле, в противном случае возвращает значение S_FALSE.

## <a name="remarks"></a>Примечания
 Чтобы получить атрибут байт, связанных с помощью настраиваемого атрибута, вызовите [GetCustomAttributeByName](../../../extensibility/debugger/reference/idebugcustomattributequery2-getcustomattributebyname.md) метод.

## <a name="see-also"></a>См. также
- [IDebugCustomAttributeQuery2](../../../extensibility/debugger/reference/idebugcustomattributequery2.md)