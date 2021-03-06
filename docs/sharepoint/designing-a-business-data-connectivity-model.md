---
title: Проектирование Business Data Connectivity Model | Документация Майкрософт
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- BDC [SharePoint development in Visual Studio], designing a model
- Business Data Connectivity service [SharePoint development in Visual Studio], designing a model
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 8f322d18afdb8e14ee87ae31d30dd6bdd57b07c5
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "63431286"
---
# <a name="design-a-business-data-connectivity-model"></a>Проектирование модели подключения к бизнес-данным
  Можно разработать модель для службы бизнес-данным (BDC), добавив в файл модели сущностей и методы. Сущность описывает коллекцию полей данных. Например сущность может представлять таблицу в базе данных. Метод выполняет задачи, такие как добавление, удаление или обновление данных в виде сущностей. Дополнительные сведения см. в разделе [интегрировать бизнес-данные в SharePoint](../sharepoint/integrating-business-data-into-sharepoint.md).

## <a name="add-entities"></a>Добавление сущностей
 Сущность можно добавить, перетащив или скопировав **сущности** из Visual Studio **элементов** в конструктор BDC. Дополнительные сведения см. в разделе [Как Добавление сущности в модель](../sharepoint/how-to-add-an-entity-to-a-model.md).

 Определение полей сущности в классе. Например, можно добавить поле с именем `Address` для `Customer` класса. Можно добавить новый класс в проект или использовать существующий класс, созданный с помощью других средств, таких как реляционный конструктор объектов (O/R Designer). Имя объекта и имя класса, который представляет сущность, не должны совпадать. Связывают данный класс сущности, при определении методов в модели.

## <a name="add-methods"></a>Добавьте методы
 Служба BDC вызывает методы в модели, когда просмотра, добавления, изменения или удаления информации в списке или веб-часть, основанный на модели. Необходимо добавить метод в модель для каждой задачи, которая может выполнять пользователь. Создайте методы, при выборе любой из пяти основных типов методов из **Подробности метода BDC** окна. В следующей таблице описаны пять основных методов модели BDC.

|Метод|Описание|
|------------|-----------------|
|Служба поиска|Возвращает коллекцию экземпляров сущности. Вызывается, когда пользователь открывает список или веб-части. Дополнительные сведения см. в разделе [Как Добавление метода Finder](../sharepoint/how-to-add-a-finder-method.md).|
|Конкретный поиск|Возвращает конкретный экземпляр сущности. Вызывается, когда пользователь просматривает сведения конкретного элемента в списке. Дополнительные сведения см. в разделе [Как Добавление определенного метода Finder](../sharepoint/how-to-add-a-specific-finder-method.md).|
|Создание|Добавляет новые данные в источник данных сущности. Вызывается при нажатии **новый элемент** кнопка на ленте списка, который основан на модели. Дополнительные сведения см. в разделе [Как Добавление метода Creator](../sharepoint/how-to-add-a-creator-method.md).|
|Обновление|Изменяет данные в виде списка. Вызывается, когда пользователи обновлять сведения в виде списка. Дополнительные сведения см. в разделе [Как Добавление метода Updater](../sharepoint/how-to-add-an-updater-method.md).|
|Удаление|Удаляет данные. Вызывается при удалении элемента из списка. Дополнительные сведения см. в разделе [Как Добавление метода Deleter](../sharepoint/how-to-add-a-deleter-method.md).|

## <a name="define-method-parameters"></a>Определение параметров метода
 При создании метода, Visual Studio добавляет входные и выходные параметры, которые подходят для типа метода. Эти параметры являются всего лишь заполнители. В большинстве случаев необходимо изменить параметры, чтобы они передавали или вернуть правильный тип данных. Например по умолчанию метод поиска возвращает строку. В большинстве случаев вы хотите изменить возвращаемый параметр метода поиска таким образом, чтобы он возвращает коллекцию сущностей. Этого можно, изменив дескриптор типа параметра. Дескриптор типа является коллекцией атрибутов, описывающий тип данных параметра. Дополнительные сведения см. в разделе [Как Определение дескриптора типа параметра](../sharepoint/how-to-define-the-type-descriptor-of-a-parameter.md).

 Visual Studio позволяет копировать дескрипторы типов между параметрами в модели. Например, можно определить дескриптор типа с именем `CustomerTD` для возвращаемого параметра `GetCustomer` метод. Вы можете скопировать `CustomerTD` введите дескриптор в **Обозреватель BDC**, а затем вставьте этот дескриптор типа во входной параметр `CreateCustomer` метод. Это предотвращает не нужно задавать тот же дескриптор типа более одного раза.

## <a name="method-instances"></a>Метод экземпляров
 При создании метода, Visual Studio добавляет метод экземпляра по умолчанию. Экземпляр метода является ссылкой на метод, а также значения по умолчанию для параметров. Один метод может иметь несколько экземпляров метода. Каждый экземпляр представляет собой сочетание сигнатуру метода и набор значений по умолчанию. Дополнительные сведения см. в разделе [Как Определение дескриптора типа параметра](../sharepoint/how-to-define-the-type-descriptor-of-a-parameter.md).

 При запуске проекта, экземпляры метода появляются в раскрывающемся списке над списком SharePoint. Пользователи могут выбирать экземпляры метода для просмотра данных.

 Чтобы добавить значения по умолчанию для экземпляра метода, необходимо непосредственно изменить XML модели. Дополнительные сведения см. в разделе [DefaultValue](http://go.microsoft.com/fwlink/?LinkID=169279).

## <a name="add-filter-descriptors"></a>Добавление дескриптора фильтра
 Пользователям модели может потребоваться для извлечения экземпляров сущности, которые отвечают некоторым условиям. Чтобы включить эту функцию, можно добавить дескриптор фильтра к методу. Дескрипторы фильтра позволяют пользователям модели фильтровать метод результирующих наборов, передав значения для методов, перед их выполнением. Дополнительные сведения см. в разделе [Как Добавление параметров фильтра для действия, чтобы ограничить экземпляры из внешней системы](http://go.microsoft.com/fwlink/?LinkID=169267).

 SharePoint предоставляет несколько функций, которые пользователи могут вводить значения фильтра. Например веб-частей бизнес-данных предоставляют текстовое поле фильтра. Пользователи могут ограничить данные в списке путем ввода значения в это текстовое поле. Дополнительные сведения о том, как добавление дескриптора фильтра в метод, см. в разделе [как: Добавление дескриптора фильтра в метод Finder](../sharepoint/how-to-add-a-filter-descriptor-to-a-finder-method.md).

### <a name="filter-descriptor-properties"></a>Свойства дескриптора фильтра
 Необходимо задать значение **связанный дескриптор типа**, **имя**, и **тип** свойства дескриптора фильтра. Все остальные свойства являются необязательными.

 **Связанный дескриптор типа** свойство связывает дескриптор фильтра для входного параметра. Когда пользователь вносит значение фильтра, служба BDC передает это значение в метод с помощью входного параметра.

 **Тип** свойство описывает шаблон фильтрации, который вы хотите использовать. В SharePoint, выбранный шаблон фильтрации влияет на текст, отображаемый в интерфейс пользователя (UI). Например, для фильтрации шаблона сравнения, текст **равен** отображается как элемент управления выше веб-часть данных Business. Дополнительные сведения о каждом шаблоне фильтрации см. в разделе [Types of Filters Supported с BDC](http://go.microsoft.com/fwlink/?LinkId=169287).

 Дополнительные сведения о свойствах дескриптора фильтра см. в разделе [дескриптора фильтра](http://go.microsoft.com/fwlink/?LinkID=169280).

### <a name="provide-default-values"></a>Предоставить значения по умолчанию
 В некоторых случаях пользователь может не обеспечивать значение фильтра. Можно предоставлять значение по умолчанию, добавив значение по умолчанию для экземпляра метода, или установив значение по умолчанию в коде метода. Дополнительные сведения о том, как добавить значение по умолчанию для экземпляра метода, см. в разделе [экземпляр метода](http://go.microsoft.com/fwlink/?LinkID=169282). Пример того, как задать значение по умолчанию для входного параметра в коде метода, см. в разделе [как: Добавление дескриптора фильтра в метод Finder](../sharepoint/how-to-add-a-filter-descriptor-to-a-finder-method.md).

## <a name="validate-the-model"></a>Проверка модели
 Модель можно проверить во время разработки. Visual Studio позволяет выявить проблемы, которые могут помешать модели ожидаемое поведение. Эти проблемы отображаются в Visual Studio **список ошибок**.

 Можно проверить модель, открыв контекстное меню для конструктора BDC, а затем выбрав **Validate**. Если модель содержит ошибки, они отображаются в **список ошибок**. Можно быстро переместить курсор в код, который содержит ошибку, дважды щелкнув на нее в списке. Кроме того, вы можете **F8** или **Shift**+**F8** ключей, чтобы перемещаться вперед и назад по в списке ошибок.

 Ошибки проверки могут возникать при нарушении правила модели каким-либо образом. Например если **IsCollection** дескриптора типа свойству **true**, но дочерний дескриптор типа не существует, отображается ошибка проверки. Может потребоваться обратиться к правилам модели BDC, чтобы понять некоторые ошибки, которые отображаются в Visual Studio **список ошибок**. Дополнительные сведения о правилах модели BDC см. в разделе [BDCMetadata Schema](http://go.microsoft.com/fwlink/?LinkID=169275).

## <a name="debug-the-solution-that-contains-the-model"></a>Отладка решения, содержащего модель
 Выполнять отладку кода, как отладка любого кода в Visual Studio. Для отладки кода, установите точки останова в любом месте в коде, а затем запустите отладчик. Visual Studio открывает сайт SharePoint. В SharePoint создайте список или веб-части, который использует бизнес-данных. Затем можно пошаговое выполнение кода. Дополнительные сведения об отладке проектов SharePoint см. в разделе [решений SharePoint, устранение неполадок](../sharepoint/troubleshooting-sharepoint-solutions.md).

 Также можно отлаживать код в пользовательских сборках, добавляемые в проект. Тем не менее для отладки кода в пользовательской сборке, необходимо добавить сборку в пакет решения. Дополнительные сведения см. в разделе [Как Добавление и удаление дополнительных сборок](../sharepoint/how-to-add-and-remove-additional-assemblies.md).

 Дополнительные сведения о добавлении пользовательской сборки в проект, см. в разделе [как: Добавление пользовательской сборки в возможность BDC](../sharepoint/how-to-include-a-custom-assembly-in-a-bdc-feature.md).

### <a name="configure-bdc-security"></a>Настройка безопасности BDC
 Может потребоваться изменить параметры безопасности в SharePoint для отладки решения. Чтобы изменить эти параметры, откройте подключение службы бизнес-данных приложения в SharePoint 2010 сайт центра администрирования Web. В **задание разрешений метаданных Store** » диалогового окна «Добавление учетной записи пользователя, а затем выберите любой из следующих параметров:

|Задача|Параметр|
|----------|------------|
|Для развертывания моделей для службы BDC.|Правка|
|Для создания списков и веб-частей с помощью внешних типов контента (сущностей) в модели.|Выбирается в клиентах|
|Для создания, чтения, обновления и удаления данных сущностей.|Выполнение|

 Дополнительные сведения об этих параметрах см. в разделе [Business Data Connectivity service management](http://go.microsoft.com/fwlink/?LinkID=178883).

 Также можно задать разрешения для отдельных моделей или внешних типов контента. Дополнительные сведения о том, как устанавливать разрешения безопасности для модели, см. в разделе [Управление моделью BDC](http://go.microsoft.com/fwlink/?LinkID=178884). Дополнительные сведения о том, как устанавливать разрешения безопасности для внешнего типа содержимого, см. в разделе [управления внешнем типе контента](http://go.microsoft.com/fwlink/?LinkID=178885).

> [!NOTE]
> Используйте эти параметры для отладки решения на локальном сервере SharePoint. Дополнительные сведения о том, как настроить параметры безопасности, относящихся к BDC, на рабочем сервере SharePoint см. в разделе [Общие сведения о безопасности Business Data Connectivity Services](http://go.microsoft.com/fwlink/?LinkID=178886).

### <a name="retract-models-that-become-corrupt"></a>Отзыв поврежденных моделей
 При первом запуске отладчика Visual Studio развертывает всю модель в SharePoint. После этого каждый раз Visual Studio обновляет модель в SharePoint, любые изменения, внесенные между развертываниями.

 Могут возникнуть ситуации, где требуется Visual Studio полностью отозвать модель из SharePoint. Например модель может быть повреждена.  Чтобы повторно развернуть модель в SharePoint, задайте **добавочное обновление** свойства модели для **False**, и затем запустите отладчик. **Добавочное обновление** свойство отображается в **свойства** окно при выборе узла, представляющего модель в **Обозреватель BDC**. По умолчанию является имя модели **BdcModel1**.

### <a name="change-identifier-names-of-entities-in-the-model"></a>Измените имена идентификаторов сущностей в модели
 При изменении имени идентификатора после развертывания модели, может появиться ошибка развертывания. Не удается устранить эту ошибку, задав **добавочное обновление** свойства модели для **False**. Необходимо вручную отозвать модель и затем повторите развертывание. Дополнительные сведения см. в разделе [решений SharePoint, устранение неполадок](../sharepoint/troubleshooting-sharepoint-solutions.md). Этой ошибки можно избежать, задав **добавочное обновление** свойства **False** до первого развертывания модели.

## <a name="locate-documentation-for-bdc-model-elements"></a>Найдите документацию для элементов модели BDC
 Visual Studio добавляет XML-элемент модели для каждой сущности, метод или другой элемент, который создается. Атрибуты элемента отображаются в виде свойств **свойства** окна. Сведения о элементы и атрибуты, создаваемые в Visual Studio при разработке модели, см. в разделе [BDCMetadata Schema](http://go.microsoft.com/fwlink/?LinkID=169275).

## <a name="related-topics"></a>См. также

|Заголовок|Описание|
|-----------|-----------------|
|[Обзор средств проектирования модели BDC](../sharepoint/bdc-model-design-tools-overview.md)|Средства, которые можно использовать для визуального проектирования модели для BDC.|
|[Практическое руководство. Добавление сущности в модель](../sharepoint/how-to-add-an-entity-to-a-model.md)|Показано, как добавить в модель внешних типов контента или сущностей.|
|[Практическое руководство. Добавление метода Finder](../sharepoint/how-to-add-a-finder-method.md)|Показано, как добавить метод, позволяющий пользователям просматривать список сущностей в списке или веб-части.|
|[Практическое руководство. Добавление определенного метода Finder](../sharepoint/how-to-add-a-specific-finder-method.md)|Показано, как добавить метод, позволяющий пользователям просматривать сведения о конкретной сущности.|
|[Практическое руководство. Добавление метода Creator](../sharepoint/how-to-add-a-creator-method.md)|Показано, как добавить метод, который позволяет пользователям добавлять записи к источнику данных непосредственно из списка или веб-части.|
|[Практическое руководство. Добавление метода Deleter](../sharepoint/how-to-add-a-deleter-method.md)|Показано, как добавить метод, позволяющий пользователям удалять данные из источника данных с помощью параметров в интерфейс пользователя (UI), списка или веб-части.|
|[Практическое руководство. Добавление метода Updater](../sharepoint/how-to-add-an-updater-method.md)|Показано, как добавить метод, который позволяет пользователям изменять данные в источнике данных непосредственно из списка или веб-части.|
|[Практическое руководство. Добавление параметра в метод](../sharepoint/how-to-add-a-parameter-to-a-method.md)|Показано, как использовать окно сведений о метод в Visual Studio для добавления ввода и возвращаемые параметры метода.|
|[Практическое руководство. Определение дескриптора типа параметра](../sharepoint/how-to-define-the-type-descriptor-of-a-parameter.md)|Показано, как определить типы данных параметров в модели.|
|[Практическое руководство. Определение экземпляра метода](../sharepoint/how-to-define-a-method-instance.md)|Показано, как создать экземпляр метода, выполняющего BDC.|
|[Практическое руководство. Добавление дескриптора фильтра в метод Finder](../sharepoint/how-to-add-a-filter-descriptor-to-a-finder-method.md)|Показано, как разрешить пользователям ограничить количество возвращаемых методом поиска экземпляров.|
|[Создание ассоциации между сущностями](../sharepoint/creating-an-association-between-entities.md)|Описывает, как можно определить отношения между сущностями в модели. Веб-частей бизнес-данных, внешних списков и пользовательских приложений можно отобразить отношения данных в пользовательском интерфейсе (UI).|
|[Практическое руководство. Создание ассоциации между сущностями](../sharepoint/how-to-create-an-association-between-entities.md)|Показано, как определить связи между сущностями в модели.|
|[Пошаговое руководство: Создание внешнего списка в SharePoint с помощью бизнес-данных](../sharepoint/walkthrough-creating-an-external-list-in-sharepoint-by-using-business-data.md)|Содержит пошаговые инструкции, в которых показано, как создать и проверить модель, которая отображает контактов во внешнем списке SharePoint.|
|[Интеграция бизнес-данных в SharePoint](../sharepoint/integrating-business-data-into-sharepoint.md)|Обзор создания и проектирования моделей для службы BDC.|
