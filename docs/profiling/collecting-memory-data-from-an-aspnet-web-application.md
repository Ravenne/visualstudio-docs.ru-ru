---
title: Сбор данных по использованию памяти для веб-приложений ASP.NET с помощью командной строки профилировщика | Документы Майкрософт
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- .NET memory profiling method
- profiling tools,.NET memory method
ms.assetid: 57acf2b0-327a-4c0e-8078-ac2f6d99457d
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- aspnet
ms.openlocfilehash: a9e6bfce4b9137283a9413168fe320e292195c12
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "63405871"
---
# <a name="collect-memory-data-from-an-aspnet-web-application-by-using-the-profiler-command-line"></a>Сбор данных об использовании памяти для веб-приложений ASP.NET с помощью командной строки профилировщика
В этом разделе описаны процедуры и параметры сбора данных по выделению памяти и времени существования объектов для веб-приложения ASP.NET с помощью программы командной строки **VSPerfCmd**.

> [!NOTE]
> Программа **VSPerfCmd** предоставляет полный доступ к возможностям Средств профилирования, включая приостановку и возобновление профилирования, а также сбор дополнительных данных счетчиков производительности Windows и процессора. Если эти возможности не нужны, можно воспользоваться программой командной строки **VSPerfASPNETCmd**. В отличие от средства [VSPerfCmd](../profiling/vsperfcmd.md), нет необходимости устанавливать переменные среды и перезагружать компьютер. Дополнительные сведения см.в статье [Быстрое профилирование веб-сайтов с помощью средства VSPerfASPNETCmd](../profiling/rapid-web-site-profiling-with-vsperfaspnetcmd.md).

## <a name="common-tasks"></a>Типичные задачи

|Задача|Связанное содержимое|
|----------|---------------------|
|**Подключение профилировщика к выполняющемуся приложению ASP.NET**|-   [Практическое руководство. Присоединение профилировщика к веб-приложению ASP.NET для сбора данных об использовании памяти](../profiling/how-to-attach-the-profiler-to-an-aspnet-web-application-to-collect-memory-data-by-using-the-command-line.md)|
|**Инструментирование статически скомпилированных двоичных файлов**|-   [Практическое руководство. Инструментирование статически скомпилированного приложения ASP.NET и сбор данных об использовании памяти](../profiling/how-to-instrument-a-statically-compiled-aspnet-app-and-collect-memory-data.md)|
|**Инструментирование динамически скомпилированных двоичных файлов**|-   [Практическое руководство. Инструментирование динамически скомпилированного приложения ASP.NET и сбор данных об использовании памяти](../profiling/how-to-instrument-a-dynamically-compiled-aspnet-web-application-and-collect-memory-data.md)|

## <a name="related-tasks"></a>Связанные задачи

### <a name="profile-aspnet-web-applications"></a>Профилирование веб-приложений ASP.NET

|Задача|Связанное содержимое|
|----------|---------------------|
|**Профилирование с помощью метода выборки**|-   [Сбор статистики приложения с помощью метода выборки](../profiling/collecting-application-statistics-for-aspnet-using-the-profiler-sampling-method.md)|
|**Профилирование с помощью метода инструментирования**|-   [Сбор подробных сведений о времени с помощью инструментирования](../profiling/collecting-detailed-timing-data-aspnet-profiler-instrumentation-method.md)|
|**Профилирование конфликтов ресурсов и действий потока**|-   [Сбор данных параллелизма](../profiling/collecting-concurrency-data-for-an-aspnet-web-application.md)|

### <a name="profile-net-framework-memory-data"></a>Профилирование данных об использовании памяти .NET Framework

|Задача|Связанное содержимое|
|----------|---------------------|
|**Профилирование автономных (клиентских) приложений**|-   [Сбор данных об использовании памяти .NET Framework](../profiling/collecting-dotnet-framework-memory-data-for-stand-alone-applications.md)|
|**Профилирование служб**|-   [Сбор данных об использовании памяти .NET](../profiling/collecting-memory-data-from-dotnet-framework-services-by-using-the-profiler-command-line.md)|

### <a name="analyze-net-memory-data-views-and-reports"></a>Анализ представлений и отчетов данных об использовании памяти .NET
- [Представления данных в памяти .NET](../profiling/dotnet-memory-data-views.md)

## <a name="reference"></a>Ссылка
- [Справочник по средствам профилирования из командной строки](../profiling/command-line-profiling-tools-reference.md)