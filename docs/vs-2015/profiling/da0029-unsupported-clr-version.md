---
title: 'DA0029: неподдерживаемая версия среды CLR | Документы Майкрософт'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
f1_keywords:
- vs.performance.29
- vs.performance.rules.DA0029
helpviewer_keywords:
- vs.performance.29
- vs.performance.DA0029
- vs.performance.rules.DA0029
ms.assetid: 76247259-c6f3-44c4-b3f9-d8dac16b5e0d
caps.latest.revision: 11
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 532427618f476e1e187d8a1c88749810f9d157c9
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MTE95
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54803544"
---
# <a name="da0029-unsupported-clr-version"></a>DA0029: неподдерживаемая версия среды CLR
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

ИД правила | DA0029 |  
| Категория | Использование средств профилирования |  
| Метод профилирования | Профилирование из командной строки |  
| Сообщение | Во время сбора обнаружена неподдерживаемая версия среды CLR. Управляемые символы могут разрешаться неправильно.|  
| Тип правила | Сведения. |  
  
## <a name="cause"></a>Причина  
 Предпринята попытка профилирования приложения, в котором используется платформа [!INCLUDE[net_v11_long](../includes/net-v11-long-md.md)], не поддерживаемая Средствами профилирования.  
  
## <a name="rule-description"></a>Описание правила  
 Это предупреждение выдается по той причине, что Средствам профилирования не удается разрешить символы в управляемом коде, выполняющемся в приложении. Средства профилирования не могут разрешать символы управляемого кода в приложениях для платформы [!INCLUDE[net_v11_long](../includes/net-v11-long-md.md)].  
  
## <a name="how-to-fix-violations"></a>Устранение нарушений  
 Отсутствует.
