---
title: Задача CallTarget | Документы Майкрософт
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- CallTarget task [MSBuild]
- MSBuild, CallTarget task
ms.assetid: bb1fe2c4-4383-436f-8326-c24cc4a46150
caps.latest.revision: 9
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d12fde1654c4645a6b543e44f8c48f273f32349b
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "47570335"
---
# <a name="calltarget-task"></a>Задача CallTarget
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Последнюю версию этого раздела можно найти в [задача CallTarget](https://docs.microsoft.com/visualstudio/msbuild/calltarget-task).  
  
  
Вызывает указанные целевые объекты в файле проекта.  
  
## <a name="task-parameters"></a>Параметры задачи  
 В следующей таблице приводятся параметры задачи `CallTarget`.  
  
|Параметр|Описание|  
|---------------|-----------------|  
|`RunEachTargetSeparately`|Необязательный выходной параметр `Boolean`.<br /><br /> Если задано значение `true`, модуль [!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)] вызывается по одному разу для каждого целевого объекта. Если задано значение `false`, модуль [!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)] вызывается однократно для сборки всех целевых объектов. Значение по умолчанию — `false`.|  
|`TargetOutputs`|Необязательный выходной параметр <xref:Microsoft.Build.Framework.ITaskItem>`[]` .<br /><br /> Содержит выходные данные всех собранных целевых объектов.|  
|`Targets`|Необязательный параметр `String[]` .<br /><br /> Указывает один или несколько целевых объектов для сборки.|  
|`UseResultsCache`|Необязательный параметр `Boolean` .<br /><br /> Если задано значение `true`, возвращается кэшированный результат (при его наличии).<br /><br /> **Примечание**. При выполнении задачи MSBuild ее выходные данные кэшируются в области (ProjectFileName, GlobalProperties)[TargetNames] в виде списка элементов сборки.|  
  
## <a name="remarks"></a>Примечания  
 Если заданный в `Targets` целевой объект завершается сбоем, а `RunEachTargetSeparately` имеет значение `true`, задача продолжает сборку оставшихся целевых объектов.  
  
 Если вы хотите выполнить сборку целевых объектов по умолчанию, используйте [задачу MSBuild](../msbuild/msbuild-task.md) и задайте для параметра `Projects` значение `$(MSBuildProjectFile)`.  
  
 Помимо перечисленных выше параметров, эта задача наследует параметры от класса <xref:Microsoft.Build.Tasks.TaskExtension>, который, в свою очередь, наследует от класса <xref:Microsoft.Build.Utilities.Task>. Список этих дополнительных параметров и их описания см. в статье [TaskExtension Base Class](../msbuild/taskextension-base-class.md).  
  
## <a name="example"></a>Пример  
 Приведенный ниже пример вызывается `TargetA` из `CallOtherTargets`.  
  
```  
<Project DefaultTargets="CallOtherTargets"  
    xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  
    <Target Name="CallOtherTargets">  
        <CallTarget Targets="TargetA"/>  
    </Target>  
  
    <Target Name="TargetA">  
        <Message Text="Building TargetA..." />  
    </Target>  
  
</Project>  
```  
  
## <a name="see-also"></a>См. также  
 [Справочные сведения о задачах](../msbuild/msbuild-task-reference.md)   
 [Целевые объекты](../msbuild/msbuild-targets.md)


