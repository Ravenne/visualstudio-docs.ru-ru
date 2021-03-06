---
title: Как выполнить Сбор данных счетчиков производительности ЦП | Документация Майкрософт
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.performance.property.cpucounters
helpviewer_keywords:
- profiling tools, using portable CPU counters
- performance tools, portable CPU counters
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: c607263c6b6f6472258aaeab1c3187efaf30a120
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62973985"
---
# <a name="how-to-collect-cpu-counter-data"></a>Как выполнить Сбор данных счетчиков производительности ЦП

Счетчик событий ЦП используется для сбора данных о производительности конкретного оборудования. В этой статье демонстрируется сбор данных счетчиков событий при использовании метода профилирования "Инструментирование".

Могут возникать два типа событий счетчиков ЦП:

- переносимые события — события ЦП, которые могут регистрироваться независимо от конкретного ЦП;

- события платформы — события ЦП, которые привязаны к конкретному ЦП.

  Переносимые события включают общие события, такие как завершенные инструкции и неостановленные циклы, события буферизации ЦП, события ветвления и события кэша L2. Доступные счетчики событий платформы определяются изготовителем процессора.

  Категории событий могут совместно использоваться счетчиками переносимых событий и событий платформы. Например, следующие категории данных часто используются для обоих типов:

- события памяти;

- события внешнего интерфейса;

- события ветвления.

  Данные счетчиков производительности можно собирать в профилировщике двумя способами:

- сбор данных из одного или нескольких счетчиков при профилировании путем инструментирования;

- указание события счетчика в качестве интервала выборки при профилировании путем выборки. Дополнительные сведения см. в разделе [Как Выбор событий выборки](../profiling/how-to-choose-sampling-events.md).

## <a name="to-collect-cpu-performance-counter-data-when-you-profile-by-instrumentation"></a>Сбор данных счетчика производительности ЦП при профилировании путем инструментирования

1. В разделе **Страницы свойств** сеанса производительности щелкните **Счетчики ЦП**.

2. Установите флажок **Сбор данных счетчиков ЦП**.

3. Разверните дерево **Доступные счетчики производительности**, чтобы найти нужные события выборки.

4. Для каждого собираемого события выберите событие и щелкните стрелку "вправо", чтобы добавить событие в список **Выбранные счетчики**.

    > [!NOTE]
    > Дерево **Доступные счетчики производительности** отображается только в том случае, если установлен флажок **Сбор данных счетчиков ЦП**.

## <a name="see-also"></a>См. также

[Настройка сеансов анализа производительности](../profiling/configuring-performance-sessions.md)
[Свойства сеанса анализа производительности](../profiling/performance-session-properties.md)
[Счетчики ЦП и Windows](../profiling/cpu-and-windows-counters.md)
[Практическое руководство. Выбор событий выборки](../profiling/how-to-choose-sampling-events.md)