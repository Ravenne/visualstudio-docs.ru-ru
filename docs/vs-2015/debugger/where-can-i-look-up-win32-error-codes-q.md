---
title: Где можно найти коды ошибок Win32? | Документы Майкрософт
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vc.errors
dev_langs:
- FSharp
- VB
- CSharp
- C++
- C++
helpviewer_keywords:
- error codes, Win32
- Win32, error codes
ms.assetid: 8fb4ff42-b8eb-4152-b49e-b802d194b05e
caps.latest.revision: 19
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: d403315a2320589f69174109d55c8726ffd5f673
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "58990941"
---
# <a name="where-can-i-look-up-win32-error-codes"></a>Где можно найти коды ошибок Win32?
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

WINERROR.H в папке INCLUDE стандартного дистрибутива содержит определения кодов ошибок для функций Win32 API.  
  
 Кроме того, код ошибки можно посмотреть, введя код в окно **Контрольные значения** или в диалоговом окне **Быстрая проверка**. Пример:  
  
```  
0x80000004,hr  
```  
  
## <a name="see-also"></a>См. также  
 [Вопросы и ответы по отладке машинного кода](../debugger/debugging-native-code-faqs.md)   
 [Отладка машинного кода](../debugger/debugging-native-code.md)
