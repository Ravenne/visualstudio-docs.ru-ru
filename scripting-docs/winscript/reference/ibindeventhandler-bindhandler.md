---
title: IBindEventHandler::BindHandler | Документация Майкрософт
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IBindEventHandler.BindHandler
apilocation:
- scrobj.dll
helpviewer_keywords:
- IBindEventHandler::BindHandler
ms.assetid: 87909828-2224-4bb1-a6c9-dfe715ac4c9b
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 01372766eb434efe73f47b265c7984bab48ea164
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62991375"
---
# <a name="ibindeventhandlerbindhandler"></a>IBindEventHandler::BindHandler
Связывает событие объекта.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
HRESULT BindHandler(  
   LPCOLESTR   pstrEvent,  
   IDispatch*  pdisp  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `pstrEvent`  
 [in] Указывает события для обработки.  
  
 `pdisp`  
 [in] Указывает объект для обработки события.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Метод возвращает `HRESULT`. Допустимые значения включают, но не ограничиваются, значения, приведенные в следующей таблице.  
  
|Значение|Описание|  
|-----------|-----------------|  
|`S_OK`|Метод успешно выполнен.|  
  
## <a name="remarks"></a>Примечания  
 Этот метод привязывает событие для объекта.  
  
## <a name="see-also"></a>См. также  
 [Интерфейс IBindEventHandler](../../winscript/reference/ibindeventhandler-interface.md)