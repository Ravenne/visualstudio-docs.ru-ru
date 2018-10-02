---
title: 'CA2003: Не следует обрабатывать нити как потоки | Документация Майкрософт'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- CA2003
- DoNotTreatFibersAsThreads
helpviewer_keywords:
- CA2003
- DoNotTreatFibersAsThreads
ms.assetid: 15398fb1-f384-4bcc-ad93-00e1c0fa9ddf
caps.latest.revision: 18
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 6563537df74d9e392bad8c4f6ce28c85b8441546
ms.sourcegitcommit: 99d097d82ee4f9eff6f588e5ebb6b17d8f724b04
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/24/2018
ms.locfileid: "47592292"
---
# <a name="ca2003-do-not-treat-fibers-as-threads"></a>CA2003: не следует обрабатывать нити как потоки
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Последнюю версию этого раздела можно найти в [CA2003: не следует обрабатывать нити как потоки](https://docs.microsoft.com/visualstudio/code-quality/ca2003-do-not-treat-fibers-as-threads).

|||
|-|-|
|TypeName|DoNotTreatFibersAsThreads|
|CheckId|CA2003|
|Категория|Microsoft.Reliability|
|Критическое изменение|Не критическое|

## <a name="cause"></a>Причина
 Управляемый поток обрабатывается как поток Win32.

## <a name="rule-description"></a>Описание правила
 Не считайте, что управляемый поток является потоком Win32. Это волокно. Среда CLR (CLR) будет выполняться управляемые потоки как волокна в контексте реальных потоков, которые принадлежат SQL. Эти потоки могут совместно использоваться доменами приложений и даже баз данных в процессе SQL Server. С помощью управляемого потока, который будет работать в локальном хранилище, но нельзя использовать локальное хранилище неуправляемого или предполагается, что код будет работать в текущем потоке операционной системы еще раз. Не изменяйте параметры, такие как языковой стандарт потока. Не вызывайте CreateCriticalSection или CreateMutex через P/Invoke, так как они требуют, что поток, который вошел в блокировку также необходимо выйти из блокировки. Так как это не так при использовании волокон, мьютексы и критические секции Win32 будут бесполезны в SQL. Может безопасно использовать большую часть состояния управляемого объекта System.Thread. Сюда входят локальной памяти управляемого потока и текущих региональных параметров пользовательского интерфейса пользователя потока. Тем не менее модели программирования, будет невозможно изменить текущий язык и региональные параметры потока при использовании SQL; Это будет действовать через новое разрешение.

## <a name="how-to-fix-violations"></a>Устранение нарушений
 Проверьте использование потоков и соответствующим образом изменить код.

## <a name="when-to-suppress-warnings"></a>Отключение предупреждений
 Это правило не следует отключать.


