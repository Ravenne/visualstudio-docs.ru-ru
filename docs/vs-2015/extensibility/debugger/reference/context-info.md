---
title: CONTEXT_INFO | Документация Майкрософт
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- CONTEXT_INFO
helpviewer_keywords:
- CONTEXT_INFO structure
ms.assetid: 6b513f4e-e7b0-4969-adf0-2205ccc1e09b
caps.latest.revision: 12
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 5a915458c00e75f6acb62434e184170420d15aad
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "47572805"
---
# <a name="contextinfo"></a>CONTEXT_INFO
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Последнюю версию этого раздела можно найти в [CONTEXT_INFO](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/context-info).  
  
Эта структура описывает контекст памяти или контекст кода.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp#  
typedef struct _tagCONTEXT_INFO {   
   CONTEXT_INFO_FIELDS dwFields;  
   BSTR                bstrModuleUrl;  
   BSTR                bstrFunction;  
   TEXT_POSITION       posFunctionOffset;  
   BSTR                bstrAddress;  
   BSTR                bstrAddressOffset;  
   BSTR                bstrAddressAbsolute;  
} CONTEXT_INFO;  
```  
  
```csharp  
public struct CONTEXT_INFO {  
   public uint          dwFields;  
   public string        bstrModuleUrl;  
   public string        bstrFunction;  
   public TEXT_POSITION posFunctionOffset;  
   public string        bstrAddress;  
   public string        bstrAddressOffset;  
   public string        bstrAddressAbsolute;  
};  
```  
  
## <a name="members"></a>Участники  
 dwFields  
 Сочетание флагов из он [CONTEXT_INFO_FIELDS](../../../extensibility/debugger/reference/context-info-fields.md) перечисление, указывающее, какие поля заполняются **.**  
  
 bstrModuleUrl  
 Имя модуля, где находится контекст.  
  
 bstrFunction  
 Имя функции, где находится контекст.  
  
 posFunctionOffset  
 Объект [TEXT_POSITION](../../../extensibility/debugger/reference/text-position.md) структуру, которая определяет смещение строки и столбца функции, связанные с контекст кода.  
  
 bstrAddress  
 Адрес в коде, где находится данный контекст.  
  
 bstrAddressOffset  
 Смещение по адресу в коде, где находится данный контекст.  
  
 bstrAddressAbsolute  
 Абсолютный адрес в памяти, где находится данный контекст.  
  
## <a name="remarks"></a>Примечания  
 Эта структура возвращается из вызова [GetInfo](../../../extensibility/debugger/reference/idebugmemorycontext2-getinfo.md) метод.  
  
 Обычно эта структура используется поддержки **памяти** окно отладки.  
  
## <a name="requirements"></a>Требования  
 Заголовок: msdbg.h  
  
 Пространство имен: Microsoft.VisualStudio.Debugger.Interop  
  
 Сборка: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>См. также  
 [Структуры и объединения](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [GetInfo](../../../extensibility/debugger/reference/idebugmemorycontext2-getinfo.md)   
 [CONTEXT_INFO_FIELDS](../../../extensibility/debugger/reference/context-info-fields.md)   
 [TEXT_POSITION](../../../extensibility/debugger/reference/text-position.md)
