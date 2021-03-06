---
title: Практическое руководство. Подавление предупреждений при помощи пункта меню | Документация Майкрософт
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: conceptual
helpviewer_keywords:
- warnings, suppressing
- code analysis, suppressing warnings
ms.assetid: 36bd1850-dcde-4ed0-9bc3-0b83df434362
caps.latest.revision: 26
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 5097ecb0f7458e739def275d616eb344a2a6db0d
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "63426569"
---
# <a name="how-to-suppress-warnings-by-using-the-menu-item"></a>Практическое руководство. Отключение предупреждений с помощью пункта меню
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

ПРИМЕЧАНИЕ
> В источнике подавления не поддерживается для проектов веб-сайтов.  
  
 В окне анализа кода можно использовать для подавления предупреждений анализа кода. Подавление предупреждения не так же, как отключить ее. При отключении предупреждения, оно применяется только к конкретному экземпляру нарушения. Другое нарушение то же самое предупреждение будет по-прежнему отмечено в окне списка ошибок.  
  
 После выполнения анализа кода, можно указать, что один или несколько предупреждений анализа кода, которые отображаются в окне анализа кода не применяются к приложению. Например может определить, что код является ошибок. Или, возможно, так что некоторые нарушения имеют низкий приоритет и не будет исправлена в текущем цикле разработки. Независимо от причины это часто полезно указать, что предупреждение неприменимо, чтобы позволить члены команды знали, что код прошел проверку и выяснилось, что предупреждение можно игнорировать. В источнике подавление полезно, так как он позволяет поместить подавление рядом с которой создается предупреждение.  
  
 Вы можете выбрать, будет ли отображаться подавление в исходном коде или в файл глобального подавления. Некоторые подавлений необходимо поместить в файл глобального подавления. Если это так, **в исходном** параметр будет отключен.  
  
### <a name="to-suppress-a-warning-by-using-menu-item"></a>Чтобы подавить предупреждение с помощью пункта меню  
  
1. На **анализ** меню, выберите **Windows** и выберите **анализа кода**.  
  
2. В **анализа кода** окно, выберите подавить предупреждение.  
  
3. Выберите действия, а затем выберите **подавить сообщения**, а затем выберите либо **в исходном** или **в файле проекта для блокируемых предупреждений**.  
  
     Предупреждения подавляются и отображаются в окне анализа кода перечеркнутым.  
  
> [!NOTE]
> Подавления, у которых нет целевого объекта отображаются в файле глобального подавления.
