---
title: Создание автономной установки
description: Узнайте, как установить Visual Studio в автономном режиме в случае ненадежного подключения к Интернету или низкой пропускной способности.
ms.date: 04/16/2019
ms.custom: seodec18
ms.topic: conceptual
f1_keywords:
- offline installation [Visual Studio]
- offline install [Visual Studio]
- layout [Visual Studio]
ms.assetid: f8625d5e-f6ea-4db0-83c0-619b77fab3cf
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.prod: visual-studio-windows
ms.technology: vs-installation
ms.openlocfilehash: f6e7c09eee52bd2ac48ccf5c51da59066ca72288
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62974126"
---
# <a name="create-an-offline-installation-of-visual-studio"></a>Создание автономной установки Visual Studio

::: moniker range="vs-2017"

Visual Studio 2017 поддерживает различные конфигурации сети и компьютера. Мы рекомендуем использовать [веб-установщик Visual Studio](https://visualstudio.microsoft.com/vs/older-downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=vs+2017+download)&mdash; — небольшой файл, в который входят все последние исправления и функции&mdash;, но понимаем, что это не всегда возможно.

::: moniker-end

::: moniker range="vs-2019"

Visual Studio 2019 поддерживает различные конфигурации сети и компьютера. Мы рекомендуем использовать [веб-установщик Visual Studio](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019)&mdash; — небольшой файл, в который входят все последние исправления и функции&mdash;, но понимаем, что это не всегда возможно.

::: moniker-end

Например, у вас может быть ненадежное подключение к Интернету или низкая пропускная способность. В этом случае у вас есть несколько вариантов: вы можете воспользоваться новым компонентом Download all, then install (Скачать все и установить), чтобы загрузить необходимые для установки файлы, или создать локальный кэш файлов с помощью командной строки.

> [!NOTE]
> Если вы являетесь администратором предприятия и вам нужно развернуть Visual Studio в сети клиентских рабочих станций, которые отделены от Интернета брандмауэром, см. руководства по [созданию сетевой установки Visual Studio](../install/create-a-network-installation-of-visual-studio.md) и [установке сертификатов, требуемых для автономной установки Visual Studio](../install/install-certificates-for-visual-studio-offline.md).

## <a name="use-the-download-all-then-install-feature"></a>Использование компонента Download all, then install (Скачать все и установить)

::: moniker range="vs-2017"

[**Новые возможности в версии 15.8**](/visualstudio/releasenotes/vs2017-relnotes-v15.8#install): загрузив веб-установщик, выберите в установщике Visual Studio Installer новый компонент **Download all, then install** (Скачать все и установить). После этого продолжите установку.

   ![Параметр Download all, then install (Скачать все и установить)](media/download-all-then-install.png)

::: moniker-end

::: moniker range="vs-2019"

загрузив веб-установщик, выберите в установщике Visual Studio Installer новый компонент **Download all, then install** (Скачать все и установить). После этого продолжите установку.

   ![Параметр Download all, then install (Скачать все и установить)](media/vs-2019/download-all-then-install-from-installer.png)

::: moniker-end

Параметр Download all, then install (Скачать все и установить) позволяет скачать Visual Studio в виде отдельного установщика для компьютера, на который он скачивается. Это позволяет безопасно отключится от Интернета перед установкой Visual Studio.

> [!IMPORTANT]
> Не используйте этот параметр, чтобы создать автономный кэш для передачи на другой компьютер. Он не предназначен для этого. <br><br>Вы можете создать автономный (локальный) кэш для установки Visual Studio на другом компьютере. Сведения о создании локального кэша см. в разделе [Использование командной строки для создания локального кэша](#use-the-command-line-to-create-a-local-cache) этой статьи, а сведения о создании сетевого кэша — в статье [Создание сетевой установки Visual Studio](../install/create-a-network-installation-of-visual-studio.md).

## <a name="use-the-command-line-to-create-a-local-cache"></a>Использование командной строки для создания локального кэша

Скачав небольшой загрузчик, откройте командную строку, чтобы создать локальный кэш. После этого установите Visual Studio из локального кэша. (При этом ISO-файлы для предыдущих версий будут заменены.)

Ниже описывается порядок действий.

### <a name="step-1---download-the-visual-studio-bootstrapper"></a>Шаг 1. Скачивание начального загрузчика Visual Studio

Для выполнения этого действия необходимо подключение к Интернету.

Прежде всего следует скачать загрузчик Visual Studio для выбранного выпуска Visual Studio. Файл установки &mdash;или загрузчик&mdash; должны иметь одно из перечисленных ниже имен или похожее.

::: moniker range="vs-2017"

| Выпуск                    | Файл                                                                    |
|----------------------------|-------------------------------------------------------------------------|
| Visual Studio Community    | [vs_community.exe](https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=community&rel=15&utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=offline+install&utm_content=download+vs2017)       |
| Visual Studio Professional | [vs_professional.exe](https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=professional&rel=15&utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=offline+install&utm_content=download+vs2017) |
| Visual Studio Enterprise   | [vs_enterprise.exe](https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=enterprise&rel=15&utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=offline+install&utm_content=download+vs2017)     |

::: moniker-end

::: moniker range="vs-2019"

| Выпуск                    | Файл                                                                    |
|----------------------------|-------------------------------------------------------------------------|
| Visual Studio Community    | [vs_community.exe](https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=community&rel=16&utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=offline+install&utm_content=download+vs2019)       |
| Visual Studio Professional | [vs_professional.exe](https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=professional&rel=16&utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=offline+install&utm_content=download+vs2019) |
| Visual Studio Enterprise   | [vs_enterprise.exe](https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=enterprise&rel=16&utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=offline+install&utm_content=download+vs2019)     |

::: moniker-end

### <a name="step-2---create-a-local-install-cache"></a>Шаг 2. Создание локального кэша установки

Для выполнения этого действия необходимо подключение к Интернету.

> [!IMPORTANT]
> Visual Studio Community требуется активировать в течение 30 дней после установки. Для этого нужно подключение к Интернету.

Откройте командную строку и выполните одну из команд, приведенных в примерах ниже. В этих примерах предполагается, что вы используете выпуск Visual Studio Community. Для других выпусков измените команду соответствующим образом.

> [!TIP]
> Чтобы предотвратить ошибку, убедитесь, что путь к полной установке содержит менее 80 символов.

- Для разработки веб-приложений .NET или классических приложений .NET выполните следующую команду:

   ```cmd
    vs_community.exe --layout c:\vslayout --add Microsoft.VisualStudio.Workload.ManagedDesktop --add Microsoft.VisualStudio.Workload.NetWeb --add Component.GitHub.VisualStudio --includeOptional --lang en-US
    ```

- Для разработки классических приложений .NET и решений Office выполните следующую команду:

   ```cmd
    vs_community.exe --layout c:\vslayout --add Microsoft.VisualStudio.Workload.ManagedDesktop --add Microsoft.VisualStudio.Workload.Office --includeOptional --lang en-US
    ```

- Для разработки классических приложений C++ выполните следующую команду:

   ```cmd
    vs_community.exe --layout c:\vslayout --add Microsoft.VisualStudio.Workload.NativeDesktop --includeRecommended --lang en-US
    ```

- Чтобы создать локальный макет с полным набором компонентов (это будет довольно долго&mdash;ведь компонентов у нас _очень много_), выполните следующую команду:

   ```cmd
    vs_community.exe --layout c:\vslayout --lang en-US
    ```

  > [!NOTE]
  > Для установки полного макета Visual Studio потребуется как минимум 35 ГБ дискового пространства. См. руководство по [использованию параметров командной строки для установки Visual Studio](use-command-line-parameters-to-install-visual-studio.md), где описано, как создать макет, содержащий только выбранные компоненты для установки.

Если вы хотите установить язык, отличный от английского, выберите нужный языковой стандарт вместо `en-US` в поле [List of language locales](#list-of-language-locales) (Список языковых стандартов). Если потребуется, используйте [список доступных компонентов и рабочих нагрузок](workload-and-component-ids.md) для дополнительной настройки кэша установки.

### <a name="step-3---install-visual-studio-from-the-local-cache"></a>Шаг 3. Установка Visual Studio из локального кэша

> [!TIP]
> При запуске установки из локального кэша используются локальные версии каждого из этих файлов. Но если во время установки вы выберете компоненты, которые отсутствуют в кэше, программа установки попытается загрузить их из Интернета.

Чтобы установить только те файлы, которые вы уже скачали, все параметры командной строки должны совпадать с теми, которые вы использовали для создания макета кэша. Предположим, что вы создали макет кэша с помощью следующей команды:

```cmd
vs_community.exe --layout c:\vslayout --add Microsoft.VisualStudio.Workload.ManagedDesktop --add Microsoft.VisualStudio.Workload.NetWeb --add Component.GitHub.VisualStudio --includeOptional --lang en-US
```

В этом случае используйте для запуска установки следующую команду.

```cmd
c:\vslayout\vs_community.exe --add Microsoft.VisualStudio.Workload.ManagedDesktop --add Microsoft.VisualStudio.Workload.NetWeb --add Component.GitHub.VisualStudio --includeOptional
```

> [!NOTE]
> Если возникает ошибка, указывающая на недопустимую подпись, вам нужно установить обновленные сертификаты. Откройте папку "Сертификаты" в автономном кэше. Дважды щелкните каждый файл сертификата и выполните инструкции в мастере диспетчера сертификатов. Если он предложит ввести пароль, оставьте это поле пустым.

### <a name="list-of-language-locales"></a>Список языковых стандартов

| **Язык-языковой стандарт** | **Язык** |
| ----------------------- | --------------- |
| cs-CZ | Чешский |
| de-DE | Немецкий |
| en-US | Английский |
| es-ES | Испанский |
| fr-FR | Французский |
| it-IT | Итальянский |
| ja-JP | Японский |
| ko-KR | Корейский |
| pl-PL | Польский |
| pt-BR | Португальский - Бразильская |
| ru-RU | Русский |
| tr-TR | Турецкий |
| zh-CN | Китайский (упрощенное письмо) |
| zh-TW | Китайский (традиционное письмо) |

[!INCLUDE[install_get_support_md](includes/install_get_support_md.md)]

## <a name="see-also"></a>См. также

- [Создание сетевой установки Visual Studio](../install/create-a-network-installation-of-visual-studio.md)
- [Установка сертификатов, необходимых для установки Visual Studio в автономном режиме](../install/install-certificates-for-visual-studio-offline.md)
- [Использование параметров командной строки для установки Visual Studio](use-command-line-parameters-to-install-visual-studio.md)
- [Идентификаторы рабочих нагрузок и компонентов Visual Studio](workload-and-component-ids.md)
