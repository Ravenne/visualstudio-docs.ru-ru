---
title: Безопасность
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- code access security, coding errors
- security [.NET Framework], about security
ms.assetid: 318c34ce-f643-468c-83a1-843196f5d845
caps.latest.revision: 24
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: f89e9a58d1ea501b9d92a44eead5e343cc7c014b
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MTE95
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2019
ms.locfileid: "57866941"
---
# <a name="security-in-visual-studio"></a>Безопасность в Visual Studio
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Вопросы безопасности должны рассматриваться на всех этапах разработки приложения — от проектирования до развертывания. Начните работу с запуска Visual Studio в наиболее безопасном режиме. См. раздел [Разрешения пользователей](../ide/user-permissions-and-visual-studio.md).

 Для успешной разработки безопасного приложения следует ознакомиться с основными понятиями безопасности и средствами защиты платформ, для которых разрабатывается приложение. Кроме того, необходимо понимать приемы безопасного кодирования.

## <a name="understanding-security"></a>Общее представление о безопасности
 [Безопасность](http://msdn.microsoft.com/library/9a9621d7-8883-4a4f-a874-65e8e09e20a6) Описание безопасности при доступе к коду, безопасности на основе ролей, а также политик и средств безопасности в .NET Framework.

## <a name="coding-for-security"></a>Безопасное кодирование
 Большинство ошибок кодирования, которые приводят к уязвимости системы безопасности, происходит из-за неправильных допущений разработчиков при работе с вводимыми пользователем данными или из-за неполного понимания принципов работы платформы, для которой разрабатывается приложение.

 [Правила написания безопасного кода](http://msdn.microsoft.com/library/4f882d94-262b-4494-b0a6-ba9ba1f5f177) Правила классификации компонентов для решения вопросов безопасности.

 [Рекомендации по безопасности](http://msdn.microsoft.com/library/86acaccf-cdb4-4517-bd58-553618e3ec42) Описание переполнения буфера и общая картина функциональности проверки безопасности в Microsoft Visual C++, которая включается с помощью флага времени компиляции /GS.
