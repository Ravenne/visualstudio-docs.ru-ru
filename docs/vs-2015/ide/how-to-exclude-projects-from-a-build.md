---
title: Практическое руководство. Исключение проектов из сборки | Документация Майкрософт
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: conceptual
ms.assetid: 17a837ca-5db9-46cd-b5a7-b14ad1d2c47d
caps.latest.revision: 8
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 6a0b46a4aaa780357faa38a9ee4b01d04b1a0ba1
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2019
ms.locfileid: "60110938"
---
# <a name="how-to-exclude-projects-from-a-build"></a>Практическое руководство. Исключение проектов из сборки
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Вы можете создать решение без сборки всех проектов, которые оно содержит. Например, можно исключить проект, который прерывает сборку. После исследования и разрешения проблем можно будет построить этот проект.  
  
 Проект исключается с помощью следующих подходов.  
  
- Временное удаление проекта из активной конфигурации решения.  
  
- Создание конфигурации решения, которая не содержит проект.  
  
  Дополнительные сведения см. в разделе [Общие сведения о конфигурациях построения](../ide/understanding-build-configurations.md).  
  
### <a name="to-temporarily-remove-a-project-from-the-active-solution-configuration"></a>Временное удаление проекта из активной конфигурации решения  
  
1. В строке меню последовательно выберите пункты **Сборка**и **Диспетчер конфигураций**.  
  
2. В таблице **Конфигурации проектов** найдите проект, который требуется исключить из сборки.  
  
3. В столбце **Сборка** для проекта снимите флажок.  
  
4. Нажмите кнопку **Закрыть**, а затем выполните повторную сборку решения.  
  
### <a name="to-create-a-solution-configuration-that-excludes-a-project"></a>Создание конфигурации решения, которая исключает проект  
  
1. В строке меню последовательно выберите пункты **Сборка**и **Диспетчер конфигураций**.  
  
2. В списке **Активная конфигурация решения** выберите **\<Создать>**.  
  
3. В поле **Имя** введите имя конфигурации решения.  
  
4. В списке **Копировать параметры из** выберите конфигурацию решения, на основе которой хотите построить новую конфигурацию (например, **Отладка**), и затем нажмите кнопку **ОК**.  
  
5. В диалоговом окне **диспетчера конфигураций** снимите флажок в столбце **Сборка** для проекта, который требуется исключить, и нажмите кнопку **Закрыть**.  
  
6. В панели инструментов **Стандартная** убедитесь, что новая конфигурация является активной в поле **Конфигурация решения**.  
  
7. В строке меню последовательно выберите пункты **Сборка**, **Перестроить решение**.  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о конфигурациях построения](../ide/understanding-build-configurations.md)   
 [Практическое руководство. Создание и изменение конфигураций](../ide/how-to-create-and-edit-configurations.md)   
 [Практическое руководство. Сборка с использованием нескольких конфигураций](../ide/how-to-build-multiple-configurations-simultaneously.md)
