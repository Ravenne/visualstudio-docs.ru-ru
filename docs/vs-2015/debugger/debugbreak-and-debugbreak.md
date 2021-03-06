---
title: DebugBreak и __debugbreak | Документация Майкрософт
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- DebugBreak
dev_langs:
- FSharp
- VB
- CSharp
- C++
- C++
helpviewer_keywords:
- debugging [C++], DebugBreak function
- DebugBreak function
- breakpoints, DebugBreak function
ms.assetid: 9787c795-df94-4f48-bc8d-3bf899b67421
caps.latest.revision: 26
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: c7d26d78cf5e1995c25560e70e46ee4f6fde3a25
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "58993877"
---
# <a name="debugbreak-and-debugbreak"></a>DebugBreak и __debugbreak
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Вызов функции DebugBreak Win32 или встроенной функции [__debugbreak](http://msdn.microsoft.com/library/1d1e1c0c-891a-4613-ae4b-d790094ba830) можно разместить в любом месте кода. Вызов `DebugBreak` или `__debugbreak` эквивалентен установке точки останова в этом месте программы.  
  
 Поскольку `DebugBreak` — это системная функция, на компьютере должны быть установлены системные отладочные символы, гарантирующие правильное отображение информации стека вызовов после приостановки выполнения. В противном случае сведения стека вызовов, отображаемые в отладчике, могут выйти за пределы одного кадра. При использовании `__debugbreak` символы не требуются.  
  
## <a name="see-also"></a>См. также  
 [Встроенные объекты компилятора](http://msdn.microsoft.com/library/48bb9929-7d78-4fd8-a092-ae3c9f971858)   
 [Безопасность отладчика](../debugger/debugger-security.md)   
 [Отладка машинного кода](../debugger/debugging-native-code.md)   
 [Указание файлов символов (.pdb) и файлов с исходным кодом](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md)
