---
title: IDiaSymbol::get_acceleratorPointerTags | Документация Майкрософт
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
dev_langs:
- C++
ms.assetid: 30e13cee-e511-49ec-affd-99b0097071b2
caps.latest.revision: 6
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: c1724ee3e81ac00ed048f323105842361ec22bc7
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62827298"
---
# <a name="idiasymbolgetacceleratorpointertags"></a>IDiaSymbol::get_acceleratorPointerTags
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Возвращает все значения тега указатель сочетаний клавиш, которые соответствуют на функцию C++ AMP accelerator заглушки.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT get_acceleratorPointerTags(   
   DWORD          cnt,  
   DWORD*         pcnt,  
   DWORD*         pPointerTags);  
```  
  
#### <a name="parameters"></a>Параметры  
 `cnt`  
 [in] Размер выходного массива `pPointerTags`.  
  
 `pcnt`  
 [out] Число тегов указатель сочетаний клавиш в C++ функции заглушки AMP сочетаний клавиш.  
  
 `pPointerTags`  
 [out] Объект `DWORD` указатель на массив, заполненный со значениями тегов accelerator указатель в C++ функции заглушки AMP сочетаний клавиш.  
  
## <a name="return-value"></a>Возвращаемое значение  
 В случае успешного выполнения возвращает `S_OK`; в противном случае возвращает `S_FALSE` или код ошибки.  
  
## <a name="remarks"></a>Примечания  
 Этот метод вызывается на `IDiaSymbol` интерфейс, который соответствует функции заглушки accelerator C++ AMP.  
  
## <a name="see-also"></a>См. также  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
