---
title: Фильтрация представлений отчетов | Документы Майкрософт
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- profiling tools, configuring
ms.assetid: 820cf192-7fd6-4bee-9a51-aa69154aca85
caps.latest.revision: 14
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 344a2dbe0e629f62f609806008b963be2be058a1
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MTE95
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2019
ms.locfileid: "60108741"
---
# <a name="filtering-report-views"></a>Фильтрация представлений отчетов
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Чтобы ограничить данные профилирования, отображаемые в представлениях отчета о производительности и экспортируемые в файлы отчетов, можно применить фильтры к файлам данных профилирования. Отчет можно ограничить данными, полученными между двумя метками времени. Кроме того, можно ограничиться данными определенных процессов или потоков. Фильтры можно сохранить в файле, а затем создать фильтр в другом файле данных профилирования, импортировав в него сохраненный фильтр.  
  
 Кроме того, отчет можно ограничить определенным отрезком времени, воспользовавшись графической временной шкалой в представлении сводки. См. раздел [Практическое руководство. Фильтрация представлений отчетов на сводной временной шкале](../profiling/how-to-filter-report-views-from-the-summary-timeline.md).  
  
 Сведения об исключении системного кода и кода сторонних производителей из отчета см. в разделе [Практическое руководство. Фильтрация представлений отчетов средств профилирования для отображения в режиме "Только мой код"](../profiling/how-to-filter-profiling-tools-report-views-to-display-just-my-code.md).  
  
## <a name="procedures"></a>Процедуры  
  
#### <a name="to-create-a-profiler-report-filter"></a>Создание фильтра отчетов профилировщика  
  
1. Если окно фильтра просмотра отчетов о производительности не отображается, щелкните значок **Показать фильтр** на панели инструментов в представлении отчета о производительности.  
  
     Фильтр представления отчета о производительности — это таблица. Каждая строка этой таблицы соответствует предложению фильтра. В фильтр можно добавить столько предложений, сколько нужно.  
  
2. Для каждого предложения, которое необходимо добавить в фильтр, выберите или введите значения в указанных ниже полях строки.  
  
    |Поле|Описание|  
    |-----------|-----------------|  
    |**И/или**|Выберите **и**, если результат должен совпадать с ситуацией, когда данное и следующее предложение являются истинными. Выберите **или**, если результат должен совпадать либо с истинностью данного предложения, либо с истинностью следующего.|  
    |**Поле**|Выберите поле отчета, которое будет использоваться в предложении фильтра, в списке полей данных.|  
    |**Operator**|Выберите оператор, задающий необходимое отношение между полем и значением в предложении.<br /><br /> =    Равно<br /><br /> <>  Не равно<br /><br /> <    Меньше чем<br /><br /> >    Больше чем<br /><br /> <=  Меньше или равно<br /><br /> >=  Больше или равно|  
    |**Значение**|Выберите или введите значение для поиска. В списках для некоторых полей отображаются доступные значения соответствующего поля.|  
  
3. 
  
#### <a name="to-create-a-profiler-report-filter-from-the-marks-report-view"></a>Создание фильтра отчета профилировщика в представлении отчета по меткам  
  
1. На панели инструментов в представлении отчета о производительности выберите в списке **Текущее представление** пункт **Метки**.  
  
    Отобразится отчет профилировщика "Метки".  
  
2. Выберите событие трассировки событий Windows или событие выборки, которое необходимо использовать в качестве отправной точки отчета.  
  
3. Нажав и удерживая клавишу CTRL, щелкните событие, которое вы хотите использовать в качестве конечной точки отчета.  
  
4. Щелкните правой кнопкой мыши и выберите один из следующих параметров:  
  
   - **Добавить фильтр по меткам** — создает предложения фильтра, в которых в качестве поля фильтра используется столбец "Метка".  
  
   - **Добавить фильтр по меткам времени** — создает предложения фильтра, в которых в качестве поля фильтра используется столбец "Метка времени в миллисекундах".  
  
     Оба варианта используются для фильтрации текущего файла данных в одних и тех же начальной и конечной точках. При экспорте фильтра для использования в других отчетах лучше может подходить один из вариантов.  
  
#### <a name="to-load-an-existing-filter-from-a-file"></a>Загрузка существующего фильтра из файла  
  
1. На панели инструментов в представлении отчета о производительности щелкните **Импортировать фильтр**.  
  
     Откроется диалоговое окно **Загрузить фильтр**.  
  
2. Укажите расположение и имя файла фильтра (VSPF) для загрузки.  
  
#### <a name="to-execute-a-filter"></a>Выполнение фильтра  
  
- На панели инструментов в представлении отчета о производительности щелкните **Выполнить фильтр**.  
  
#### <a name="to-stop-a-filter-that-is-taking-too-long-to-execute"></a>Остановка фильтра, выполнение которого длится слишком долго  
  
- На панели инструментов в представлении отчета о производительности щелкните **Остановить фильтр**.  
  
#### <a name="to-remove-a-filter-on-a-report-view"></a>Удаление фильтра в представлении отчета  
  
1. Удалите строки предложений в фильтре представления отчета о производительности.  
  
2. На панели инструментов в представлении отчета о производительности щелкните **Выполнить фильтр**.  
  
#### <a name="to-save-a-filter-to-a-file"></a>Сохранение фильтра в файле  
  
1. На панели инструментов в представлении отчета о производительности щелкните **Экспортировать фильтр**.  
  
     Откроется диалоговое окно **Сохранить фильтр**.  
  
2. Укажите расположение и имя файла фильтра (VSPF) для сохранения.  
  
## <a name="see-also"></a>См. также раздел  
 [Настройка представлений отчетов средств производительности](../profiling/customizing-performance-tools-report-views.md)
