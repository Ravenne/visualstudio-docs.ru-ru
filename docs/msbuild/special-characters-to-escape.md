---
title: Знаки, требующие отключения их специального значения | Документация Майкрософт
ms.date: 11/04/2016
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- special characters to escape
- msbuild, special characters to escape
ms.assetid: 5b5172c3-41e4-4f38-a16f-2aeac831a5fc
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 1ed6be5b3beb394f4e9486ecdca973aa28c97f92
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62993191"
---
# <a name="special-characters-to-escape"></a>Знаки, требующие отключения их специального значения
Специальные знаки необходимо экранировать только в том случае, если они имеют особое значение в контексте, в котором используются. Например, звездочка (*) является специальным символом только в атрибутах "Включить" и "Исключить" определения элемента или при вызове <xref:Microsoft.Build.Tasks.CreateItem>. Во всех остальных случаях звездочка считается символом звездочки. Если не требуется экранировать звездочки в файлах проекта, использование их в таком виде не приносит никакого вреда.

 Вместо специального знака используйте нотацию %\<xx>, где \<xx> представляет собой шестнадцатеричное значение символа ASCII. Например, чтобы использовать символ звездочки (*) как буквенный символ, используйте значение `%2A`.

 Полный список специальных символов для экранирования см. далее.

|Знак|Описание|
|---------------|-----------------|
|%|Знак процента, используемый для ссылки на метаданные.|
|$|Знак доллара, используемый для ссылки на свойства.|
|@|Знак at, используемый для ссылки на списки элементов.|
|(|Открывающая скобка, используемая в списках.|
|)|Закрывающая скобка, используемая в списках.|
|\`|Апостроф (или деление), используемый в условиях и других выражениях.|
|;|Точка с запятой — разделитель элементов списка.|
|?|Вопросительный знак — подстановочный знак, используемый при описании файловой спецификации в разделе включение/исключение элемента.|
|*|Звездочка — подстановочный знак, используемый при описании файловой спецификации в разделе включение/исключение элемента.|

## <a name="see-also"></a>См. также
- [Практическое руководство. Пропуск специальных знаков в MSBuild](../msbuild/how-to-escape-special-characters-in-msbuild.md)
- [Справочные сведения о MSBuild](../msbuild/msbuild-reference.md)