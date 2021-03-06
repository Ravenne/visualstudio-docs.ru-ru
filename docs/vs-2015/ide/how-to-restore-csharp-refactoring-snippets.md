---
title: Практическое руководство. Восстановление фрагментов кода для оптимизации в C# | Документы Майкрософт
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- unsafe expansion
- expansions, unsafe
ms.assetid: 12114273-7f2f-43d0-abcb-2d4711a3a68d
caps.latest.revision: 24
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 9f81514db881ad26a5fa827b0bde11df2467f23d
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MTE95
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2019
ms.locfileid: "60050816"
---
# <a name="how-to-restore-c-refactoring-snippets"></a>Практическое руководство. Восстановление фрагментов кода для оптимизации в C#
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Операции рефакторинга в C# основываются на фрагментах кода, находящихся в следующем каталоге:  
  
 *Каталог установки*\Microsoft Visual Studio 14.0\VC#\Snippets\\*код языка*\Refactoring  
  
 Если этот каталог Refactoring или какие либо файлы в нем удалены или повреждены, то операции рефакторинга C# могут не работать в интегрированной среде разработки. Описанные ниже процедуры позволяют восстановить фрагменты кода для рефакторинга в C#.  
  
### <a name="to-verify-c-refactoring-snippets-are-available-through-the-code-snippet-manager"></a>Проверка наличия фрагментов кода для рефакторинга в C# с помощью диспетчера фрагментов кода  
  
1. В меню **Сервис** выберите пункт **Диспетчер фрагментов кода**.  
  
2. В диалоговом окне **Диспетчер фрагментов кода** выберите вариант **Visual C#** в раскрывающемся списке **Язык**.  
  
     В древовидном представлении списка папок должна появиться папка **Refactoring**.  
  
### <a name="to-restore-refactoring-see-comment-in-code-snippet-manager"></a>Восстановление функции рефакторинга с помощью примечания в диспетчере фрагментов кода  
  
1. Если папка **Refactoring** в древовидном представлении списка папок в диспетчере фрагментов кода отсутствует, выполните описанную ниже процедуру, чтобы добавить фрагменты кода для рефакторинга в диспетчер фрагментов кода.  
  
2. В меню **Сервис** выберите пункт **Диспетчер фрагментов кода**.  
  
3. В диалоговом окне **Диспетчер фрагментов кода** выберите вариант **Visual C#** в раскрывающемся списке **Язык**.  
  
4. Нажмите кнопку **Добавить**. Откроется диалоговое окно **Каталог фрагментов кода**, с помощью которого можно найти и указать каталог, который нужно добавить в диспетчер фрагментов кода.  
  
5. Найдите папку **Refactoring**, путь к которой следующий:  
  
     *Каталог установки*\Microsoft Visual Studio 14.0\VC#\Snippets\\*код языка*\Refactoring  
  
     Фактический путь подобен представленному ниже для установки по умолчанию:  
  
     C:\Program Files\Microsoft Visual Studio 14.0\VC#\Snippets\1033\Refactoring.  
  
6. Нажмите кнопку **Открыть** в диалоговом окне **Каталог фрагментов кода** и затем нажмите кнопку **ОК** в диспетчере фрагментов кода.  
  
## <a name="see-also"></a>См. также раздел  
 [Фрагменты кода Visual C#](../ide/visual-csharp-code-snippets.md)   
 [Рефакторинг (C#)](../csharp-ide/refactoring-csharp.md)   
 [Фрагменты кода](../ide/code-snippets.md)
