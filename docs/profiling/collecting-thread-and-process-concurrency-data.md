---
title: Сбор данных о параллелизме потоков и процессов | Документы Майкрософт
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- concurrency profiling method
- Profiling Tools, concurrency method
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 2c3310a87a4b25e560ea5303553e3eb75c0da001
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62831536"
---
# <a name="collect-thread-and-process-concurrency-data"></a>Сбор данных о параллелизме потоков и процессов

Метод профилирования параллелизма Средств профилирования Visual Studio позволяет собирать данные о конфликтах ресурсов, которые содержат информацию о каждом событии синхронизации. Эти события принуждают функцию в профилируемом приложении ожидать доступ к ресурсу.

Метод профилирования параллелизма можно задать с помощью одной из приведенных ниже процедур.

- На первой странице мастера профилирования щелкните **Параллелизм**.
- На странице **Общие** диалогового окна свойств сеанса анализа производительности выберите **Параллелизм**.
- На панели инструментов **обозревателя производительности** в списке **Метод** щелкните пункт **Параллелизм**.

## <a name="common-tasks"></a>Типичные задачи

Дополнительные параметры можно указать в диалоговом окне _Сеанс производительности_**страницы свойств** сеанса анализа производительности. Чтобы открыть это диалоговое окно, выполните указанные ниже действия.

- В **обозревателе производительности**щелкните правой кнопкой мыши имя сеанса анализа производительности и выберите пункт **Свойства**.

В задачах в приведенной ниже таблице описываются параметры, которые можно задать в диалоговом окне _Сеанс производительности_**Страницы свойств** при профилировании с помощью метода параллелизма.

|Задача|Связанное содержимое|
|----------|---------------------|
|На странице **Общие** задайте сведения об имени создаваемого файла данных профилирования (VSP).|- [Практическое руководство. Настройка параметров имени файла с данными о производительности](../profiling/how-to-set-performance-data-file-name-options.md)|
|На странице **Запуск** укажите приложение для запуска, если в решении с кодом содержится несколько проектов исполняемых файлов (EXE).|- [Практическое руководство. Определение двоичного файла для запуска](../profiling/how-to-specify-the-binary-to-start.md)|
|На странице **Взаимодействие уровней** добавьте данные вызова ADO.NET в сеанс профилировщика.|- [Сбор данных о взаимодействии уровней](../profiling/collecting-tier-interaction-data.md)|
|На странице **Счетчики Windows** выберите один или несколько счетчиков производительности операционной системы, значения которых будут добавляться в данные профилирования в качестве меток.|- [Практическое руководство. Сбор данных счетчиков производительности Windows](../profiling/how-to-collect-windows-counter-data.md)|
|На странице **Дополнительно** укажите версию среды выполнения .NET Framework для профилирования, если модули приложения используют несколько версий. По умолчанию профилируется первая загруженная версия.|- [Практическое руководство. Определение среды выполнения .NET Framework](../profiling/how-to-specify-the-dotnet-framework-runtime.md)|