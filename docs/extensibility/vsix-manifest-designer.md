---
title: Конструктор манифеста VSIX | Документация Майкрософт
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- VS.Sdk.VsixManifestEditor
helpviewer_keywords:
- vsixmanifest
- vsix manifest
- manifest designer
ms.assetid: 5a691e77-cf91-430d-90ea-361d9031ef83
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 84f82ab6e5cca57a1fabd600cecc7a5ee505c150
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "63411099"
---
# <a name="vsix-manifest-designer"></a>Конструктор манифеста VSIX
Изменяет файл манифеста пакета VSIX, который задает режим установки для расширения Visual Studio.

 **Конструктор манифеста VSIX** сопоставляется базовой схемы VSIX. Каждый элемент в схеме можно задать с помощью соответствующего элемента управления в конструкторе. Дополнительные сведения о схеме см. в разделе [Справочник по схеме 2.0 расширения VSIX](../extensibility/vsix-extension-schema-2-0-reference.md).

 Чтобы открыть **конструктор манифеста VSIX**, найдите *source.extension.vsixmanifest* файл **обозревателе решений**и откройте файл. Если файл не содержит допустимый XML-код, не открывается конструктор манифеста.

> [!NOTE]
> *Source.extension.vsixmanifest* файл — это выходные данные для *extension.vsixmanifest* при построении пакета.

## <a name="uielement-list"></a>Список элементов пользовательского интерфейса
 **Конструктор манифеста VSIX** содержит четыре раздела, которые соответствуют следующие элементы верхнего уровня схемы:

- Метаданные

- Целевые объекты установки

- Ресурсы

- Зависимости

  Область заголовка содержит следующие элементы управления.

  **Название продукта** описывает имя расширения.

  **Идентификатор продукта** указывает уникальные идентификационные данные для этого пакета.

  **Автор** имя автора модуля.

  **Версия** указывает номер версии расширения.

  **Метаданных** вкладка содержит следующие элементы управления.

  **Описание** предоставляет текстовое описание модуля, который будет отображаться в **Диспетчер расширений**.

  **Язык** задает язык по умолчанию для пакета, который соответствует текстовые данные в манифесте. `Language` Атрибут соответствует соглашению кода среды выполнения (CLR) языкового стандарта common языка для сборки ресурсов, например, en-us, en, fr-fr. По умолчанию значение нейтральный; это означает, что пакет будет запущен в любой языковой версии Visual Studio.

  **Лицензии** указывает текстовый файл, который содержит лицензию пользователя, если таковой имеется.

  **Значок** указывает графический файл (*.png*, *.bmp*, *.jpeg*, *.ico*), содержащий значок, отображаемый в **Диспетчер расширений**, если присутствует значок. Изображение значка должен быть 32 x 32 пикселя или изменении его размера для этих измерений. Если значок не указан, **Диспетчер расширений** используется значок по умолчанию.

  **Изображение для предварительного просмотра** указывает графический файл (*.png*, *.bmp*, *.jpeg*, *.ico*), содержащий изображение предварительного просмотра отображается в **Диспетчер расширений**, если присутствует изображение для предварительного просмотра. Изображение для предварительного просмотра должен быть 200 x 200 пикселей. Если изображение для предварительного просмотра указано, **Диспетчер расширений** использует образ по умолчанию.

  **Теги** добавляет теги текст, используемый для поиска подсказки.

  **Заметки о выпуске** указывает на файл (*.txt*, *.rtf*), содержащий заметки о выпуске. Также принимает URL-адрес веб-сайта, который отображает в заметках о выпуске.

  **Руководство по началу** указывает на файл (*.txt*, *.rtf*), содержащий сведения о том, как использовать расширение или содержимого в пакете VSIX. В этом руководстве отображается после завершения установки расширения. Также принимает URL-адрес веб-сайта, отображающий руководству.

  **Дополнительные сведения о URL** указывает URL-адрес веб-сайта, с дополнительными сведениями о продукте.

  **Цели установки** вкладка содержит следующие элементы управления.

  **Тип установки** перечислены **расширение Visual Studio** и **SDK расширения** объект типы установки. Параметры отличаются в зависимости от выбранного типа.

  **Расширение Visual Studio** перечислены **InstallationTarget** элементы, которые описывают, как можно установить пакет, и с какими продуктами Visual Studio можно установить это расширение. Каждого продукта отдельно идентифицируется по имени и версии или версии диапазона. Продукты можно добавляется в список, изменить и удалить. Имя и версию продукта соответствуют **идентификатор** и **версии** атрибуты связанного **InstallationTarget** элемент.

  **Диапазон версий** — ["12.0", "14.0"] и используется следующая запись:

- [-минимальной версии включительно

- ]-Максимальная версия включительно

- (-эксклюзивное Минимальная версия

- ) — максимальная версия монопольного

- Отдельная версия # — только указанной версии

  **Пакет SDK расширения** указывает глобального установку, которая не ограничена определенным продуктом и версии. **Идентификатор целевой платформы** — это платформа, такие как «Windows», что целевой платформой является. **Версия целевой платформы** является версией, например 8.0, целевой платформы. **Имя пакета SDK** и **версия пакета SDK** — имя и номер версии пакета SDK, соответственно.

  **Этот VSIX устанавливается для всех пользователей (требуются повышенные права, при установке)** Если флажок установлен, расширение установлено для всех пользователей; в противном случае оно устанавливается только для текущего пользователя.

  **Этот VSIX устанавливается с помощью установщика Windows** Если флажок установлен, расширение установлено с помощью установщика Windows (*.msi* файла); в противном случае устанавливается в качестве типичного пакета VSIX (*.vsix*  файл).

  **Активы** вкладка содержит следующие элементы управления.

  **Список активов** перечислены элементы активов, которые описывают элементы расширения или содержимое, что этот пакет поверхности. Каждого расширения или элемента содержимого указывается отдельно, источник, тип и путь. Расширения и содержимое элементов можно добавляется в список, изменения и удаления. Тип, а также путь расширения или содержимое элемента соответствует `Type` и `Path` атрибуты связанного `Asset` элемент. Известны следующие типы:

- Microsoft.VisualStudio.Package

- Microsoft.VisualStudio.MefComponent

- Microsoft.VisualStudio.ToolboxControl

- Microsoft.VisualStudio.Samples

- Microsoft.VisualStudio.ProjectTemplate

- Microsoft.VisualStudio.ItemTemplate

- Microsoft.VisualStudio.Assembly

- Microsoft.ExtensionSDK

  Чтобы добавить или изменить ресурс-контейнер, необходимо указать тип ресурса, ли ресурс является проект в текущее решение или файл в файловой системе и имя проекта. Можно также указать имя папки, в которой для внедрения.

  Можно также создать собственные типы и дать им уникальные имена.

  **Зависимости** вкладка содержит следующие элементы управления.

  **Имя источника и диапазон версий** список элементов зависимости данного пакета, которые являются другие пакеты, от которых зависит данный пакет. Если указан пакет зависимостей, он должен быть установлен до установки этого пакета; в противном случае необходимо установить этот пакет.

  Пакеты зависимостей задаются идентификатор, имя, диапазон версий, источник, и как зависимости должны быть обработаны. Каждый пакет зависимостей указывается отдельно по имени, версии и источник. Пакеты зависимостей можно добавляется в список, изменения и удаления.

  Идентификатор должен соответствовать `ID` атрибута метаданных пакета зависимостей. Источником может быть проект в текущее решение, установленные расширения или файл. **Как — разрешения зависимости** вложенных пакетов относительный путь или URL-адрес на местоположение загрузки зависимости можно установить. Идентификатор, версии и разрешение зависимостей пакета соответствуют `Id`, `Version`, и `Location` атрибуты связанного `Dependency` элемент.

## <a name="see-also"></a>См. также
- [Справочник по схеме 2.0 расширения VSIX](../extensibility/vsix-extension-schema-2-0-reference.md)
- [Составляющие пакета VSIX](../extensibility/anatomy-of-a-vsix-package.md)