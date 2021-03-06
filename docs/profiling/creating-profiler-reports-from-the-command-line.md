---
title: Создание отчетов профилировщика из командной строки | Документы Майкрософт
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: c886f8af-2014-4fec-9b24-d98b68ecafb7
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: e6a6d31d15f7f7ed533d73683a3c12d152bd7046
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62552906"
---
# <a name="create-profiler-reports-from-the-command-line"></a>Создание отчетов профилировщика из командной строки
Программа командной строки **VSPerfReport** позволяет создавать отчеты в формате *XML* или данных с разделителями-запятыми (*CSV*) из файлов данных профилирования (*VSP*). Типы отчетов VSPerfReport точно соответствуют табличным представлениям интерфейса для [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. Вы можете отфильтровать отчет, чтобы отобразить только ваш код и только сегмент файла данных профилирования. Дополнительные сведения см. в разделе [VSPerfReport](../profiling/vsperfreport.md).

 Вы также можете упростить общий доступ к файлам данных профилирования, внедрив символы в *VSP*-файлы и создав файлы предварительно проанализированных отчетов (*VSPS*), которые открываются быстрее и занимают меньше места.

## <a name="common-tasks"></a>Типичные задачи

|Задача|Связанное содержимое|
|----------|---------------------|
|**Создание базового отчета.** Создайте все типы отчетов VSPerfReport или их подмножество.|-   [Создание базовых отчетов](../profiling/creating-basic-profiling-reports-from-the-command-line.md)|
|**Сравнение двух файлов данных профилирования.** Создайте разностный отчет, который сравнивает данные производительности в двух файлах данных профилирования.|-   [Практическое руководство. Создание отчета сравнения профилировщиков с помощью командной строки](../profiling/how-to-create-a-profiler-comparison-report-from-a-command-prompt.md)|
|**Просмотр данных о трассировке вызовов и событий Windows (ETW).** Создайте отчет о трассировке вызовов, содержащий сведения о времени для каждой точки входа и выхода в функциях приложения, а также для каждого вызова других функций вашей функцией. Или создайте подробный список всех событий трассировки событий Windows, собранных в сеансе профилирования.|-   [Практическое руководство. Создание отчета трассировки вызовов](../profiling/how-to-create-a-profiling-tools-call-trace-report.md)|
|**Фильтрация отчета.** Ограничьте отчет лишь функциями в коде или определенным временем в файле данных профилирования.|-   [Практическое руководство. Фильтрация отчетов из командной строки](../profiling/how-to-filter-reports-from-the-command-line.md)|
|**Создание переносимых файлов данных профилирования.** Чтобы упростить общий доступ к данным профилирования, вы можете внедрить символы для сеанса профилирования в *VSP*-файл. Вы также можете создать файл предварительно проанализированных данных профилирования (*VSPS*), который меньше по размеру и открывается быстрее.|-   [Создание переносимых файлов данных профилирования](../profiling/creating-portable-profiling-data-files-from-the-command-line.md)|