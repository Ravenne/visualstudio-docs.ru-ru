---
title: IDiaSymbol::get_backEndBuild | Документация Майкрософт
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_backEndBuild method
ms.assetid: 423af497-9294-438e-92b4-456c6f56dc56
caps.latest.revision: 12
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 7628a76c2eb1b6d847dff9e5c32d09ad1434c8f2
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "63402232"
---
# <a name="idiasymbolgetbackendbuild"></a>IDiaSymbol::get_backEndBuild
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Получает номер построения серверной части компилятора.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp#  
HRESULT get_backEndBuild (   
   DWORD* pRetVal  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `pRetVal`  
 [out] Возвращает номер сборки серверной части. См. заметки.  
  
## <a name="return-value"></a>Возвращаемое значение  
 В случае успешного выполнения возвращает `S_OK`; в противном случае возвращает `S_FALSE` или код ошибки.  
  
> [!NOTE]
> Возвращаемое значение `S_FALSE` означает, что свойство недоступно для символа.  
  
## <a name="remarks"></a>Примечания  
 Компилятор обычно состоит из двух основных элементов: переднего плана (средство синтаксического анализа), который обрабатывает синтаксического анализа исходного кода в промежуточный форму, и серверной частью (генератор кода), который преобразует промежуточную форму в сборку. Нередко для внешнего интерфейса до имеют версию, отличную от серверной части.  
  
 Интерфейс или номер версии серверной части состоит из трех частей: \<основных >.\< дополнительный номер >. \<сборки >, где \<основных > — номер основной версии \<незначительные > — это дополнительный номер версии, и \<сборки > — номер сборки. Например, 13.10.3077.  
  
## <a name="requirements"></a>Требования  
  
|Требование|Описание|  
|-----------------|-----------------|  
|Заголовок:|dia2.h|  
|Версия:|ПАКЕТ SDK для версии 7.0|  
  
## <a name="see-also"></a>См. также  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
