---
title: Настройка целевых объектов и задач | Документы Майкрософт
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: msbuild
ms.topic: conceptual
ms.assetid: 9aabe67a-1720-4bbf-80d3-822b3ccf75c0
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 9d3ed6456ecf4ca226368338078247a10d80cee3
ms.sourcegitcommit: 53aa5a413717a1b62ca56a5983b6a50f7f0663b3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/17/2019
ms.locfileid: "59660597"
---
# <a name="configuring-targets-and-tasks"></a>Настройка целевых платформ и задач
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Целевые объекты и задачи MSBuild можно настроить для внепроцессного выполнения с помощью MSBuild, чтобы можно было определять целевые контексты, отличные от того, в котором идет выполнение. Например, на компьютере с 64-разрядной операционной системой и .NET Framework 4.5 можно создать приложение .NET Framework 2.0, предназначенное для 32-разрядной платформы. Вы также можете ориентироваться на компьютеры, где запущена платформа .NET Framework 4 или более ранней версии. Сочетание 32- или 64-разрядности и конкретной версии .NET Framework называется *целевым контекстом*.  
  
## <a name="installation"></a>Установка  
 Платформы .NET Framework 4.5 и 4.5.1 заменяют общеязыковую среду выполнения (CLR), целевые объекты, задачи и средства платформы .NET Framework 4, не переименовывая их. Платформа .NET Framework 4.5.1 устанавливается в составе [!INCLUDE[vs_dev12](../includes/vs-dev12-md.md)].  
  
 Если вы хотите установить MSBuild отдельно от Visual Studio, скачайте пакет установки на странице [скачиваемых материалов MSBuild](http://go.microsoft.com/fwlink/?LinkId=309745). Нужно также установить те версии .NET Framework, которые вы хотите использовать.  
  
## <a name="targets-and-tasks"></a>Целевые объекты и задачи  
 MSBuild запускает некоторые задачи сборки вне процесса, чтобы ориентироваться на более широкий набор контекстов.  Например, 32-разрядная MSBuild может запустить задачу сборки в 64-разрядном процессе, чтобы ориентироваться на 64-разрядный компьютер. Это поведение управляется аргументами `UsingTask` и параметрами `Task`. Целевые объекты, установленные платформой .NET Framework 4.5, задают эти аргументы и параметры, поэтому для сборки приложений в различных целевых контекстах никакие изменения не требуются.  
  
 Если вы хотите создать собственные целевой контекст, нужно задать эти аргументы и параметры соответствующим образом. Примеры см. в файлах Microsoft.Common.targets и Microsoft.Common.Tasks платформы .NET Framework 4.5.  Сведения о том, как создать настраиваемую задачу, способную работать с несколькими целевыми контекстами, или изменить существующие задачи, см. в разделе [Практическое руководство. Настройка целевых платформ и задач](../msbuild/how-to-configure-targets-and-tasks.md).  
  
## <a name="see-also"></a>См. также  
 [Настройка для различных версий](../msbuild/msbuild-multitargeting-overview.md)
