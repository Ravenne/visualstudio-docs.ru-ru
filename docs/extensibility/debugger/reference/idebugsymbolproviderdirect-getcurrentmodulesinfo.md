---
title: IDebugSymbolProviderDirect::GetCurrentModulesInfo | Документация Майкрософт
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- IDebugSymbolProviderDirect::GetCurrentModulesInfo
- GetCurrentModulesInfo
ms.assetid: b3b45ed2-ea4e-4389-b78a-11fc9796a6c1
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 1225729ceb6d1a874f4ca5bedef287ababbdb962
ms.sourcegitcommit: 50f0c3f2763a05de8482b3579026d9c76c0e226c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/09/2019
ms.locfileid: "65457444"
---
# <a name="idebugsymbolproviderdirectgetcurrentmodulesinfo"></a>IDebugSymbolProviderDirect::GetCurrentModulesInfo
Извлекает сведения о модулях в группе символов.

## <a name="syntax"></a>Синтаксис

```cpp
HRESULT GetCurrentModulesInfo(
   unsigned long * pCount,
   GUID *          ppGuids,
   DWORD *         pADIds,
   DWORD *         pCurrentState,
   IUnknown **     ppCDModItfs
);
```

```csharp
int GetCurrentModulesInfo(
   uint       pCount,
   Guid       ppGuids,
   uint       pADIds,
   uint       pCurrentState,
   out object ppCDModItfs
);
```

## <a name="parameters"></a>Параметры
 `pCount`\

 [in] Число модулей в `ppGuids` массива.

 `ppGuids`\

 [in] Массив, содержащий уникальные идентификаторы для модулей.

 `pADIds`\

 [in] Идентификаторы доменов приложений.

 `pCurrentState`\

 [in] Текущее состояние группы символов.

 `ppCDModItfs`\

 [out] Возвращает объект, содержащий модули в группе символов.

## <a name="return-value"></a>Возвращаемое значение
 В случае успешного выполнения возвращает `S_OK`; в противном случае возвращает код ошибки.

## <a name="see-also"></a>См. также
- [IDebugSymbolProviderDirect](../../../extensibility/debugger/reference/idebugsymbolproviderdirect.md)